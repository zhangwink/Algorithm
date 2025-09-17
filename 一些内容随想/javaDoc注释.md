# javaDoc注释

```java
/**
 *JavaDoc类
 *用于介绍javadoc注释
 *可以使用html标签来格式化注释内容
 *<b>粗体字符</b><br>
 *@author zzp
 *@version 1.0
 */
public class JavaDoc{
	/**
	 *示例方法
	 *
	 *@param arg1 参数1
	 *@param arg2 参数2
	 *@return 返回1
	 */
    public int method (String arg1,String arg2){
	return 1;
    }
    
    /**
     * 主函数
     * @param args 命令行参数
     */
    public static void main(String [] args){
        
    }
}
```

```java
@auther 说明后面的内容是作者姓名
@version说明后面的内容是类的版本
@param  说明后面的内容是方法的参数说明
@return 说明后面的内容是返回值说明
@throws 说明后面的内容是方法可能抛出异常说明
@see	引用其他类和方法
```

