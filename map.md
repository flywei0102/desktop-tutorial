🌟 HashMap 

    - key-value: key相当于value的一个描述或者引用
    - Map是通过get()获取对应的value，通过values()获取所有的value，而且还可以通过put进行新增键值对
    - 基于哈希表的Map接口实现
    - 底层是array结构
    - 无序，key值不可重复

intitialization:

    - Map< , > map = new HashMap<>();
    - HashMap map = new HashMap();      // 290

🌟TreeMap   

     - Map接口的基于Tree结构的实现
     - 基于红黑树实现[ ](https://github.com/julycoding/The-Art-Of-Programming-By-July/blob/master/ebook/zh/03.01.md)
     - 有序，key值可重复
     - comparator 排序[ ](https://www.liaoxuefeng.com/wiki/1252599548343744/1265117109276544)

🌟Pair<key, value> 

     - Pair保存的是一个信息对，key和value都要保存具体信息，也就是没有key和value之分
     - (不同点)
           - Pair保存的是一对key-value, 而map可以保存多对key-value
           - Pair通过getKey()/getValue()获取对应的key值和value值，没有添加键值对的操作
           - 

🌟 hashCode() 

    - 主要用于查找得快捷性 [link](https://blog.csdn.net/SEU_Calvin/article/details/52094115) 
    - hashCode是用于查找使用的，equals是用于比较两个对象是否相等
    - （通俗易懂）： 先通过HashCode来判断两个类是否放在同一个桶里，但是这个桶里可能有很多类，那么久需要再通过equals在这个桶里找到我们需要的类。
    - -------------------------------------------
    - ✨ 举例：当map集合要添加新的元素时，先调用hashCode()定位该对象应该放置的物理位置
    -      （1）如果这个位置上没有元素，就可以直接储存在这个位置
    -      （2）如果这个位置上有了元素，再调用equals()方法与新元素进行比较，相同的话就不存了
    -      （3）不相同的话，也就是发生了Hash Key相同导致冲突的情况。那么就在这个hash key的地方产       生一个链表，将所有产生相同hashCode的对象放到这个单链表上去。
    - 535
    - 应用：很多网络服务会使用哈希函数，产生一个token，标识用户的身份和权限。（如果两个不同的用户得到同一个token，就是发生了哈希碰撞，服务器会把这两个用户视为同一个人，意味着用户B可以读取和更改A的信息。黑客攻击的方法之一就是制造哈希碰撞）
    - -------------------------------------------
    - **hashCode collision**
    - 如果不同的hash key得到同一个哈希值，就发生了“哈希碰撞”
    - 防止哈希碰撞的嘴有效方法就是扩大哈希值的取值空间，从16个二进制位 -> 32个二进制位
    - 


