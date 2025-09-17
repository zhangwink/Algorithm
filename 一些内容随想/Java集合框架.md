# Java集合框架

## 导语:

​	Java 集合框架主要包括两种类型的容器，一种是集合（Collection），存储一个元素集合，另一种是图（Map），存储键/值对映射。

- 接口:  是代表集合的抽象数据类型。例如 Collection、List、Set、Map 等。之所以定义多个接口，是为了以不同的方式操作集合对象
- 实现(类): 是集合接口的具体实现 ,从本质讲他们是可重复使用的数据结构,例如ArrayList,LinkedList,HashSet,HashMap.
- 算法:是实现集合接口的对象里的方法一些有用的计算,例如:搜索和排序,这些算法实现了多态

除了集合,该框架还定义了几个MAP接口和类 map对应的键和值,尽管map不是集合,但他们呢都完整的定义在集合![image-20250917185948312](C:\Users\zhangzepan\AppData\Roaming\Typora\typora-user-images\image-20250917185948312.png)

![img](https://www.runoob.com/wp-content/uploads/2014/01/java-coll-2020-11-16.png)

## Java ArrayList

这是一个可以动态修改的是数组,与普通数组的区别就是他没有固定的大小限制,可以添加或删除元素.

```java
import java.util.ArrayList;
import java.util.Collections;  // 引入 Collections 类

public class RunoobTest{
	public static void main(String []args){
        ArrayList<String> sites = new ArrayList<String >();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        System.out.println(sites);
        System.out.println(sites.get(1));//可以使用get类似于数组查询的方法
        /**修改元素
         *@param arg1 第一个参数为索引位置
         *@param arg2 第二个参数为要修改的值
         */
        sites.set(2,"Wiki");
        //删除元素
        sites.remove(3);
        //计算大小
        System.out.println(sites.size());
        
        //for-each迭代元素
        for (String i : sites) {
            System.out.println(i);
        }
        
        //Collections类也是一个非常有用的类 提供了sort()方法可以对字母书数字进行排序
		Collections.sort(sites);
    }
}
```

借此机会刚好来讲一下for-each高级的for迭代用法

```java
for (int i :myNumbers)
    等价于=====
for (int i=0;i<myNumbers;i++){
	int j=myNumbers.get(i);
}
```

## Java LinkedList

链表（Linked list）是一种常见的基础数据结构，是一种线性表，但是并不会按线性的顺序存储数据，而是在每一个节点里存到下一个节点的地址。

链表可分为单向链表和双向链表。



**以下情况使用 ArrayList :**

- 频繁访问列表中的某一个元素。
- 只需要在列表末尾进行添加和删除元素操作。

**以下情况使用 LinkedList :**

- 你需要通过循环迭代来访问列表中的某些元素。
- 需要频繁的在列表开头、中间、末尾等位置进行添加和删除元素操作。

LinkedList 继承了 AbstractSequentialList 类。

LinkedList 实现了 Queue 接口，可作为队列使用。

LinkedList 实现了 List 接口，可进行列表的相关操作。

LinkedList 实现了 Deque 接口，可作为队列使用。

LinkedList 实现了 Cloneable 接口，可实现克隆。

LinkedList 实现了 java.io.Serializable 接口，即可支持序列化，能通过序列化去传输。

实例:

```java
// 引入 LinkedList 类
import java.util.LinkedList;

public class RunoobTest {
    public static void main(String[] args) {
        LinkedList<String> sites = new LinkedList<String>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        // 使用 addFirst() 在头部添加元素
        sites.addFirst("Wiki");
        System.out.println(sites);
        
        // 使用 addLast() 在尾部添加元素
        sites.addLast("Wiki");
        
         // 使用 removeLast() 移除尾部元素
        sites.removeLast();
        
        // 使用 getFirst() 获取头部元素
        System.out.println(sites.getFirst());
        
         // 使用 getLast() 获取尾部元素
        System.out.println(sites.getLast());
    }
}
```

## Java HashSet

HashSet基于HashMap实现的 是一个不允许有重复元素的集合

HashSet允许有null值

HashSet是无序的,不会记录插入的顺序

HashSet 实现了 Set 接口

![img](https://www.runoob.com/wp-content/uploads/2020/07/java-hashset-hierarchy.png)

创建HashSet实例

```java
HAshSet<String> sites =new HashSet<String>();
```

同样的添加元素

```java
// 引入 HashSet 类      
import java.util.HashSet;

public class RunoobTest {
    public static void main(String[] args) {
    HashSet<String> sites = new HashSet<String>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Zhihu");
        sites.add("Runoob");  // 重复的元素不会被添加
        System.out.println(sites);
    }
}
```

可以使用contains()方法来判断元素是否存在于集合当中

```java
import java.util.HashSet;

public calss main{
    public static void main(String [] args){
        sites.add("GooGle");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Zhihu");
        sites.add("Runoob");  // 重复的元素不会被添加
        System.out.println(sites.contains("Taobao"));
    }
}
```

删除元素

```java
// 引入 HashSet 类      
import java.util.HashSet;

public class RunoobTest {
    public static void main(String[] args) {
    HashSet<String> sites = new HashSet<String>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Zhihu");
        sites.add("Runoob");     // 重复的元素不会被添加
        sites.remove("Taobao");  // 删除元素，删除成功返回 true，否则为 false
        System.out.println(sites);
        
        //直接删除全部
        sites.clear();
        
        //迭代HashSet
        for (String i : sites){
            System.out.println(i);
        }
    }
}
```

## Java HashMap

HashMap 是一个散列表，它存储的内容是键值对(key-value)映射。

HashMap 实现了 Map 接口，根据键的 HashCode 值存储数据，具有很快的访问速度，最多允许一条记录的键为 null，不支持线程同步。

HashMap 是无序的，即不会记录插入的顺序。

HashMap 的 key 与 value 类型可以相同也可以不同，可以是字符串（String）类型的 key 和 value，也可以是整型（Integer）的 key 和字符串（String）类型的 value。![img](https://static.jyshare.com/images/mix/java-map.svg)

创建HashMap实例

```java
HashMap<Integer,Integer>Sites =new HashMap<Integer,String>();
```

```java
// 引入 HashMap 类      
import java.util.HashMap;

public class RunoobTest {
    public static void main(String[] args) {
        // 创建 HashMap 对象 Sites
        HashMap<Integer, String> Sites = new HashMap<Integer, String>();
        // 添加键值对
        Sites.put(1, "Google");
        Sites.put(2, "Runoob");
        Sites.put(3, "Taobao");
        Sites.put(4, "Zhihu");
        System.out.println(Sites);
    }
}
```

我们可以使用 get(key) 方法来获取 key 对应的 value:

```java
// 引入 HashMap 类      
import java.util.HashMap;

public class RunoobTest {
    public static void main(String[] args) {
        // 创建 HashMap 对象 Sites
        HashMap<Integer, String> Sites = new HashMap<Integer, String>();
        // 添加键值对
        Sites.put(1, "Google");
        Sites.put(2, "Runoob");
        Sites.put(3, "Taobao");
        Sites.put(4, "Zhihu");
        System.out.println(Sites.get(3));
    }
}
```

