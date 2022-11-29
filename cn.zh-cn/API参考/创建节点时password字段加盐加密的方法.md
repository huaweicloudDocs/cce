# 创建节点时password字段加盐加密的方法<a name="add-salt"></a>

通过API创建节点时password字段需要加盐加密，具体方法如下：

>![](public_sys-resources/icon-note.gif) **说明：** 
>盐值需要根据密码的要求来设置，密码复杂度要求如下：
>-   长度为8-26位。
>-   密码至少必须包含大写字母、小写字母、数字和特殊字符（!@$%^-\_=+\[\{\}\]:,./?）中的三种。
>-   密码不能包含用户名或用户名的逆序。
>-   Windows系统密码不能包含用户名或用户名的逆序，不能包含用户名中超过两个连续字符的部分。

## Python<a name="zh-cn_topic_0264566186_section1520951304"></a>

**以下是Python 3.7.7环境下对密码进行加盐的示例步骤：**

>![](public_sys-resources/icon-note.gif) **说明：** 
>MacOS下python crypt包有兼容性问题，如碰到无法执行的情况，请在Linux下执行。

1.  根据盐值生成密文密码（在盐字符串的$符号前加上\\符号）：

    ```
    python3 -c "import crypt;print(crypt.crypt('test@123', crypt.mksalt()))"
    ```

    执行结果：

    ```
    $6$KZ2u71CD4JjQneAy$WF5dsoOjTgc9RD46i46cCL3H92LMEo78s0rHdfSLDE8PW7ylE2ICcxUGF7/8RBbnxW0crgA3ZGNFA0LLgFaYD0
    ```

2.  使用base64 encode（即为password字段值）：

    ```
    echo -n '$6$KZ2u71CD4JjQneAy$WF5dsoOjTgc9RD46i46cCL3H92LMEo78s0rHdfSLDE8PW7ylE2ICcxUGF7/8RBbnxW0crgA3ZGNFA0LLgFaYD0' | base64 | tr "\n" " " | sed s/[[:space:]]//g
    ```

    执行结果：

    ```
    JDYkS1oydTcxQ0Q0SmpRbmVBeSRXRjVkc29PalRnYzlSRDQ2aTQ2Y0NMM0g5MkxNRW83OHMwckhkZlNMREU4UFc3eWxFMklDY3hVR0Y3LzhSQmJueFcwY3JnQTNaR05GQTBMTGdGYVlEMA==
    ```


## Java<a name="zh-cn_topic_0264566186_section767592512011"></a>

**以下是Java环境下对密码进行加盐的示例步骤：**

1.  获取随机数作为生成盐值：

    ```
    	private static String getCharAndNumr(int length) {
            String val = "";
            Random random = new Random();
            for (int i = 0; i < length; i++) {
                // 输出字母还是数字
                String charOrNum = random.nextInt(2) % 2 == 0 ? "char" : "num";
                // 字符串
                if ("char".equalsIgnoreCase(charOrNum)) {
                    // 取得大写字母还是小写字母
                    int choice = random.nextInt(2) % 2 == 0 ? 65 : 97;
                    val += (char) (choice + random.nextInt(26));
                } else if ("num".equalsIgnoreCase(charOrNum)) { // 数字
                    val += String.valueOf(random.nextInt(10));
                }
            }
            return val;
        }
    ```

2.  生成盐值：

    ```
    	private static String generateSalt() {
            String salt;
            try {
                salt = "$6$" + getCharAndNumr(16);
            }catch (Exception e){
                salt = defaultSalt;
            }
    
            return salt;
        }
    ```

3.  根据盐值生成密文密码：

    ```
      public static String getSaltPassword(String password) {
            if(StringUtils.isBlank(password)) {
                throw new BizException("password is empty");
            }
    
            String salt = generateSalt();
    
            Crypt crypt = new Crypt();
            return crypt.crypt(password, salt);
        }
    ```

4.  使用base64 encode（即为password字段值）：

    ```
    (Base64.getEncoder().encodeToString(AddSaltPasswordUtil.getSaltPassword(cceNodeCreateVo.getPassword()).getBytes()))
    ```

5.  完整样例如下：

    ```
    import java.util.Base64;
    import java.util.Random;
    
    import org.apache.commons.codec.digest.Crypt;
    import org.apache.commons.lang.StringUtils;
    
    public class PassWord {
    	
    	static String defaultSalt = null;
    	
    	public static void main(String[] args) throws Exception {
    		System.out.println(Base64.getEncoder().encodeToString(PassWord.getSaltPassword("自定义password").getBytes()));
    	}	
    	
    	
    	//根据盐值生成密文密码
    	public static String getSaltPassword(String password) throws Exception {
            if(StringUtils.isBlank(password)) {
                throw new Exception("password is empty");
            }
    
            String salt = generateSalt();
    
            return Crypt.crypt(password, salt);
        }
    
    
    	
    	//生成盐值
    	private static String generateSalt() {
            String salt;
            try {
                salt = "$6$" + getCharAndNumr(16);
            }catch (Exception e){
                salt = defaultSalt;
            }
    
            return salt;
        }
    	
    	//获取随机数作为生成盐值
    	private static String getCharAndNumr(int length) {
            String val = "";
            Random random = new Random();
            for (int i = 0; i < length; i++) {
                // 输出字母还是数字
                String charOrNum = random.nextInt(2) % 2 == 0 ? "char" : "num";
                // 字符串
                if ("char".equalsIgnoreCase(charOrNum)) {
                    // 取得大写字母还是小写字母
                    int choice = random.nextInt(2) % 2 == 0 ? 65 : 97;
                    val += (char) (choice + random.nextInt(26));
                } else if ("num".equalsIgnoreCase(charOrNum)) { // 数字
                    val += String.valueOf(random.nextInt(10));
                }
            }
            return val;
        }
    }
    ```


## Go<a name="zh-cn_topic_0264566186_section94815481800"></a>

Go语言加盐方法可以参考如下两种方式实现。

-   [https://github.com/amoghe/go-crypt](https://github.com/amoghe/go-crypt)
-   [https://github.com/GehirnInc/crypt](https://github.com/GehirnInc/crypt)

