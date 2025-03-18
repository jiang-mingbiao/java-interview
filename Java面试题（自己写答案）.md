# 一、基础

##### 	<font color="red">1、Java都有哪些数据类型？基本数据类型有哪些？分别占多少字节？多少位？引用数据类型又有哪些？</font>

​		**基本数据类型：**byte（1）、short（2）、int（4）、long（8）、float（4）、double（8）、char（2）、boolean（1）
​		**引用数据类型：**数组、接口、对象

##### 	<font color="red">2、Java语言的几大特性是什么？分别怎么理解？(封装、继承、多态的好处)	</font>

​		封装：就是把对象的属性和行为看作一个整体，尽可能的隐藏内部的细节，只把可以告诉别人的公开，别人可以用我提供的功能实现需求，但不知道怎么实现的，提高了安全性。

​		继承：子类继承父类的属性和行为，并可以根据自己的需求扩展的自己的行为，这样可以提高代码的复用性。

​		多态：出现在父类指向子类，允许不同的对象对同一消息做出响应，就是同一个消息根据发送对象的不同，采用不用的行为方式。

​		抽象：表示对问题领域进行分析、设计中得出的抽象的概念，是对一系列看上去不同， 但是本质上相同的具体概念的抽象。在 Java 中抽象用 abstract 关键字来修饰，用 abstract 修饰类时，此类就不能被实例化，从这里可以看出，抽象类（接口）就是为了继承而存在的。

##### 	<font color="red">3、Java的权限修饰符有哪些？都能加在哪些地方？分别代表什么意义？</font>

​		1、public（公共的）：public是权限最大的修饰符，他可以修饰类，成员变量，成员方法，构造方法。被public修饰后，**可以再任何一个类中，不管同不同包，任意使用**。

​		2、private（私有的）：private可以修饰成员变量，成员方法，构造方法，不能修饰类(此刻指的是[外部类](https://so.csdn.net/so/search?q=外部类&spm=1001.2101.3001.7020)，内部类不加以考虑)。被private修饰的成员**只能在其修饰的本类中访问**，在其他类中不能调用，但是被private修饰的成员可以通过set和get方法向外界提供访问方式。

​		3、protected [prəˈtektɪd]（受保护的）：protected可以修饰成员变量，成员方法，构造方法，但不能修饰类(此处指的是外部类，[内部类](https://so.csdn.net/so/search?q=内部类&spm=1001.2101.3001.7020)不加以考虑)。**被protected修饰后，只能被同包下的其他类访问。如果不同包下的类要访问被protected修饰的成员，这个类必须是其子类。**

​		4、defalut（默认的）：defalut即不写任何关键字，它可以修饰类，成员变量，成员方法，构造方法。被默认权限修饰后，其**只能被本类以及同包下的其他类访问。**

##### 	<font color="red">4、什么是重写？什么是重载？</font>

​		重写：发生在子父类中，方法名，参数类型，返回值必须相同，返回值的范围小于等于父类，抛出的异常范围小于等于父类，访问的修饰符大于等于父类，如果父类被private修饰，则不能被重写。

​		重载：发生在同一个类中，方法名必须相同，参数类型不同、个数不同、顺序不同，返回值不同和修饰符可以不同。

##### 	<font color="red">5、final关键字能加在哪些地方？分别代表什么？</font>

​		对于一个final变量,如果是基本数据类型的变量,则其数值一旦在初始化之后便不能更改; 如果是引用类型的变量,则在对其初始化之后便不能再让其指向另一个对象 .
当用 final 修饰一个类时, 表明这个类不能被继承.
使用 final 方法的原因有两个:
​		a) 第一个原因是把方法锁定, 以防任何继承类修改他的含义 ;
​		b) 第二个原因是效率, 在早期的Java实现版本中，会将 final方法转为内嵌调用。但是如果方法过于庞大，可能看不到内嵌调用 带来的任何性能提升（现在的Java版本已经不需要使用final方法进行 这些优化了）。类中所有的private方法都隐式地指定为final	

##### 	<font color="red">6、static关键字能加在哪些地方？分别代表什么？</font>

​		a）修饰成员变量，将其变为类的成员变量，从而实现所有对象对于该成员共享；

​		b）修饰成员方法，将其变为类的方法，可以直接用**“类名”.“方法名”**的方式调用。常用于工具类中；

​		c）静态块用法，将多个类成员放在一起初始化，使得程序更加规整，其中理解对象的初始化过程非常关键；

​		d）静态导包，将类的方法直接导入到当前类中，从而直接使用**“方法名”**就可以直接调用该方法，；

##### 	<font color="red">7、接口中可以有哪些成员？抽象类呢？接口和抽象类又有什么区别？（注意JDK1.8接口中是可以出现非抽象方法的：default方法、静态方法）</font>

|            | 接口       | 抽象类  |
| ---------- | ---------- | ------- |
| 关键字     | implements | extends |
| 个数       | 不限       | 1个     |
| 构造函数   | 无         | 有      |
| main方法   | 无         | 有      |
| 访问修饰符 | 默认public | 任意    |

##### 	<font color="red">8、Java异常体系是什么?(编译)异常有什么区别？常见的运行时异常有哪些？</font>

异常体系：**Thorwable**类（表示可抛出）是所有异常和错误的超类，两个直接子类为**Error**和**Exception**，分别表示错误和异常。其中异常类Exception又分为**运行时异常(RuntimeException)**和**非运行时异常**， 这两种异常有很大的区别，也称之为不检查异常（Unchecked Exception）和检查异常（Checked Exception）。

1、**Error错误：**（这种错误无法处理）描述了Java运行时系统的内部错误和资源耗尽错误。一般是指虚拟机（JVM）相关的问题，如系统崩溃，虚拟机出错误等，这种错误无法恢复或不可能捕获，将导致应用程序中断，通常不处理。因为如果出现这样的内部错误，除了通告用户，并尽力使程序安全地终止之外，再也无能为力了。

2、**Exception异常：**Java的异常分为两种，checked Exception（编译时异常也叫非运行时异常）和 RuntimeException（运行时异常）。

​		a.**运行时异常**（逻辑方面）都是RuntimeException类及其子类异常，如NullPointerException、IndexOutOfBoundsException等，这些异常是不检查异常，程序中可以选择捕获处理，也可以不处理。这些异常一般是由程序逻辑错误引起的，程序应该从逻辑角度尽可能避免这类异常的发生。

​		b.**非运行时异常**（程序语法）是RuntimeException以外的异常，类型上都属于Exception类及其子类。从程序语法角度讲是必须进行处理的异常，如果不处理，程序就不能编译通过。如IOException、SQLException等以及用户自定义的Exception异常，一般情况下不自定义检查异常。

##### 	<font color="red">9、== 和 equals的异同？</font>

​		==：基本数据类型比较的是值，引用数据类型比较的是地址值

​		equals：比较的是两个字符串的内容，属于内容比较。

##### 	<font color="red">10、&与&&、|与||的区别？</font>

​		&和| ：是普通逻辑运算，需要前后都有得出结果

​		&&和||：属于短路运算符，只要前面可以得出结果，后面的就不需要执行了，能提高效率

##### 	<font color="red">11、为什么String被设计为不可变的？</font>

​		这就要看他的源码了，String类是一个被final修饰的一个类，里面就一个private final byte[] value属性，涉及到了字符串常量池，不可变的好处如下

​		1.线程安全：不可变对象是天然线程安全的，因为它们的状态在创建后不能被改变。因此，多个线程可以同时访问同一个 `String` 对象，而不需要担心线程间的同步问题

​		2.字符串池（String Pool）优化：Java 中有一个字符串常量池（String Pool），它用于减少内存开销。不可变性允许字符串对象被缓存和复用。

		3. 哈希值的缓存：`String` 对象经常被用作哈希表（如 `HashMap` 和 `HashSet`）的键。如果字符串是不可变的，其哈希值（`hashCode`）可以在第一次计算后缓存，不需要每次重新计算，提高了性能。
		3. 适合底层实现（类加载器、文件路径等）：Java 的许多底层实现都依赖于 `String`，例如类加载器、文件路径等。不可变性确保了这些核心功能的稳定性和可靠性。

##### 	<font color="red">12、StringBuffer和StringBuilder的区别是什么？</font>

​		都属于**AbstractStringBuilder**的子类，StringBuffer对方法加了同步锁或者对调用的方法加了同步锁，所以是线程安全 的。StringBuilder 并没有对方法进行加同步锁，所以是非线程安全的。

​		a）如果要操作少量数据用String

​		b）多线程操作字符串缓冲区下大量的数据用StringBuffer

​		c）单线程操作字符串缓冲区下大量的数据用StringBuilder

##### 	<font color="red">13、valueOf和toString的区别？</font>

​		1、valueOf()偏向于运算，toString()偏向于显示

​		2、对象转换时，优先调用toString()

​		3、强转字符串的情况下，优先调用toString()方法；强转数字的情况下优先调用valueOf()

​		4、正常情况下，优先调用toString()

​		5、在有运算操作符的情况下valueOf()的优先级高于toString()，这里需要注意的是当调用valueOf()方法无法运算后还是会再调用toString()方法

##### 	<font color="red">14、大量字符串用 "+" 号进行拼接效率高吗？为什么？应该用什么替代？为什么？</font>

​		不高，`String` 是不可变的，每次使用 `+` 拼接字符串，都会创建一个新的 `String` 对象。在大量字符串拼接时，这会导致频繁的对象创建和垃圾回收，浪费内存和 CPU。

**小规模字符串拼接：** 可以直接使用 `+`。

**大规模或循环中的拼接：** 推荐使用 `StringBuilder`。

**多线程环境：** 使用 `StringBuffer`。

**集合拼接：** 使用 `String.join` 或 `Collectors.joining`。

##### 	<font color="red">15、创建一个类的实例都有哪些办法？</font>

​		 a.用new 语句创建对象，这是最常用的创建对象方法。 

​		 b.调用对象的Object.clone()方法 

​		 c.运用反序列化手段，调用java.io.ObjectInputStream对象的readObject()方法。

​		 d.运用反射手段，调用Java.lang.Class或者java.lang.reflect.Constructor类的newInstance()实例方法。 

##### 	<font color="red">16、Java集合的体系是什么样的？</font>

​		![image-20221010160141401](https://github.com/jiang-mingbiao/java-interview/blob/main/img/abnormal_system.png)

##### 	<font color="red">17、Set和List分别有哪些特点？Set去重的原理？</font>

​		1、List,Set都是继承自Collection接口
​		2、List特点：元素有放入顺序，元素可重复 Set特点：元素无放入顺序，元素不可重复，重复元素会覆盖掉，（元素虽然无放入顺序，但是元素在set中的位置是有该元素的HashCode决定的，其位置其实是固定的，加入Set 的Object必须定义equals()方法 ，另外list支持for循环，也就是通过下标来遍历，也可以用迭代器，但是set只能用迭代，因为他无序，无法用下标来取得想要的值。）

​			List 以特定次序来持有元素，可有重复元素。Set 无法拥有重复元素,内部排序

​		**3.Set和List对比：**
​		Set：检索元素效率低下，删除和插入效率高，插入和删除不会引起元素位置改变。
​		List：和数组类似，List可以动态增长，查找元素效率高，插入删除元素效率低，因为会引起其他元素位置改变。

​	**去重原理：**

​		Set集合去重主要是调用 add 方法时，使用了 hashCode 方法和 equals 方法：如果在 Set集合 中找不到与该元素 hashCode 值相同的元素，则说明该元素是新元素，会被添加到 Set 集合中；如果两个元素的 hashCode 值相同，并且使用 equals 方法比较后，返回值为 true，那么就说明两个元素相同，新元素不会被添加到 Set 集合中；如果 hashCode 值相同，但是 equals 方法比较后，返回值为 false ，则两个元素不相同，新元素会被添加到 Set 集合中。

##### 	<font color="red">18、ArrayList底层原理是什么？扩容原理？</font>

​		ArrayList 的底层数据结构就是一个数组，数组元素的类型为 Object 类型，对 ArrayList 的所有操作底层都是基于数组的。

​		**1) 私有属性：**elementData 存储 ArrayList 内的元素， size 表示它包含的元素的数量。

​		**2) 构造方法：**ArrayList 提供了三种方式的构造器，**可以构造一个默认初始容量为 10 的空列表**、**构造一个指定初始容量的空列表**以及**构造一个包含指定 collection 的元素的列表**，这些元素按照该 collection 的迭代器返回它们的顺序排列的。

​		**扩容原理：**

​		ArrayList是一个数组结构的存储容器，默认情况下数组长度是10个，也可以在创建ArrayList对象的时候指定初始长度随着在程序里面不断往ArrayList里面添加数据超过十个的时候，ArrayList中就没有足够的容量去存储后续的数据，这时候ArrayList会触发自动扩容机制，自动扩容机制流程是

​		1、首先创建一个新的数据这个数组的长度是原来数组长度的1.5倍
​		2、然后使用Arrays.copyOf方法把老数组里面的数据拷贝到新的数组里面
扩容完成以后再把当前需要添加的元素加入到新的数组里面，从而完成动态扩容这样一个过程

##### 	<font color="red">19、LinkedList底层原理是什么？和ArrayList的区别是什么？</font>

​	**LinkedList**底层数据结构是一个双向链表，这里的size是元素个数，含有成员变量first和last,first和last都是LinkedList的内部类Node的实例对象，first主要用于判断是否第一次添加元素，last指向的是末尾元素。

##### 	<font color="red">20、HashMap的底层原理是什么？map添加数据put的过程？扩容原理？</font>

​		1、Jdk8 数组+链表或者数组+红黑树实现，当链表中的元素超过了 8 个以后， 会 将链表转换为红黑树，当红黑树节点 小于 等于 6 时又会退化为链表。 

​		2、 当 new HashMap():底层没有创建数组，首次调用 put()方法示时，底层创建长度 为 16 的数组，jdk8 底层的数组是：Node[],而非 Entry[]，用数组容量大小乘以加载因子得 到一个值，一旦数组中存储的元素个数超过该值就会调用 rehash 方法将数组容量增加到原 来的两倍，专业术语叫做扩容，在做扩容的时候会生成一个新的数组，原来的所有数据需要 重新计算哈希码值重新分配到新的数组，所以扩容的操作非常消耗性能.

​		 **默认的负载因子大小为 0.75，数组大小为 16。也就是说，默认情况下，那么当 HashMap 中元素个数超过 16x0.75=12 的时候，就把数组的大小扩展为 2x16=32，即扩大一倍。** 

​		3、在我们 Java 中任何对象都有 hashcode，hash 算法就是通过 hashcode 与自己进 行向右位移 16 的异或运算。这样做是为了计算出来的 hash 值足够随机，足够分散，还有 产生的数组下标足够随机， 

​	**map.put(k,v)实现原理** 

​		（1）首先将 k,v 封装到 Node 对象当中（节点）。 

​		（2）先调用 k 的 hashCode()方法得出哈希值，并通过哈希算法转换成数组的下标。 

​		（3）下标位置上如果没有任何元素，就把 Node 添加到这个位置上。如果说下标对应的位 置上有链表。此时，就会拿着 k 和链表上每个节点的 k 进行 equal。如果所有的 equals 方 法返回都是 false，那么这个新的节点将被添加到链表的末尾。如其中有一个 equals 返回了 true，那么这个节点的 value 将会被覆盖。 	

​	**map.get(k)实现原理** 

​		(1)、先调用 k 的 hashCode()方法得出哈希值，并通过哈希算法转换成数组的下标。

​		 (2)、在通过数组下标快速定位到某个位置上。重点理解如果这个位置上什么都没有，则返 回 null。如果这个位置上有单向链表，那么它就会拿着参数 K 和单向链表上的每一个节点 的 K 进行 equals，如果所有 equals 方法都返回 false，则 get 方法返回 null。如果其中一个节点的 K 和参数 K 进行 equals 返回 true，那么此时该节点的 value 就是我们要找的 value 了，get 方法最终返回这个要找的 value。

​		**4、Hash 冲突** 

​			不同的对象算出来的数组下标是相同的这样就会产生 hash 冲突，当单线链表达到一定长度 后效率会非常低。 

​		5、在**链表长度大于 8** 的时候并且**数组长度大于等于64**的时候，将链表就会变成红黑树，提高查询的效率。

##### 	<font color="red">21、concurrentHashMap原理是什么？</font>

这个问题可以从一下三个方面回答

1. ConcurrentHashMap 的整体架构 ![image-20230807140543474](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230807140543474.png)

   （如图所示），这个是 ConcurrentHashMap 在 JDK1.8 中的存储结构，它是由数组、 单向链表、红黑树组成。 

   当我们初始化一个ConcurrentHashMap实例时，默认会初始化一个长度为16的数组。由于 ConcurrentHashMap 它的核心仍然是 hash 表，所以必然会存在 hash 冲突问题。 ConcurrentHashMap 采用链式寻址法来解决 hash 冲突。 

   当 hash 冲突比较多的时候，会造成链表长度较长，这种情况会使得 ConcurrentHashMap 中数据元素的查询复杂度变成 O(n)。

   因此在 JDK1.8 中，引入了 红黑树的机制。 当数组长度大于 64 并且链表长度大于等于 8 的时候，单项链表就会转换为红黑树。 另外，随着 ConcurrentHashMap 的动态扩容，一旦链表长度小于 8，红黑树会退化 成单向链表。

2. ConcurrentHashMap 的基本功能 ![image-20230807140933682](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230807140933682.png)

   ConcurrentHashMap 本质上是一个 HashMap，因此功能和 HashMap 一样，但是 ConcurrentHashMap 在 HashMap 的基础上，提供了并发安全的实现。 并发安全的主要实现是通过对指定的 Node 节点加锁，来保证数据更新的安全性（如图 所示）。

​	3.ConcurrentHashMap 在性能方面的优化

​		如果在并发性能和数据安全性之间做好平衡，在很多地方都有类似的设计，比如 cpu 的三级缓存、mysql 的 buffer_pool、Synchronized 的锁升级等等。 ConcurrentHashMap 也做了类似的优化，主要体现在以下几个方面：

​		a. 在 JDK1.8 中，ConcurrentHashMap 锁的粒度是数组中的某一个节点，而在 JDK1.7，锁定的是 Segment，锁的范围要更大，因此性能上会更低。

​		b.引入红黑树，降低了数据查询的时间复杂度，红黑树的时间复杂度是 O(logn）

​		c.（如图所示），当数组长度不够时，ConcurrentHashMap 需要对数组进行扩 容，在扩容的实现上，ConcurrentHashMap 引入了多线程并发扩容的机制， 简单来说就是多个线程对原始数组进行分片后，每个线程负责一个分片的数据 迁移，从而提升了扩容过程中数据迁移的效率。

​		d. ConcurrentHashMap 中有一个 size()方法来获取总的元素个数，而在多线程 并发场景中，在保证原子性的前提下来实现元素个数的累加，性能是非常低的。 ConcurrentHashMap 在这个方面的优化主要体现在两个点：

​				1.当线程竞争不激烈时，直接采用 CAS 来实现元素个数的原子递增。

​				2.如果线程竞争激烈，使用一个数组来维护元素个数，如果要增加总的元素 个数，则直接从数组中随机选择一个，再通过 CAS 实现原子递增。它的核 心思想是引入了数组来实现对并发更新的负载。

##### 	<font color="red">22、JDK8对于HashMap做了哪些优化？</font>

​	

##### 	<font color="red">23、什么是socket？什么是IO/NIO/BIO/AIO？区别是什么？</font>

​		**BIO：**Block IO 同步阻塞式 IO，就是我们平常使用的传统 IO，它的特点是模式简 单使用方便，并发处理能力低。 

​		**NIO：**New IO 同步非阻塞 IO，是传统 IO 的升级，客户端和服务器端通过 Channel（通道）通讯，实现了多路复用。 

​		**AIO：**Asynchronous IO 是 NIO 的升级，也叫 NIO2，实现了异步非堵塞 IO ， 异步 IO 的操作基于事件和回调机制。

##### 	<font color="red">24、什么是反射？可以用来干嘛？列举一下反射应用场景？什么是暴力反射？</font>

​		在 Java 中的反射机制是指在运行状态中，对于任意一个类都能够知道这个类所有 的 属性和方法；并且对于任意一个对象，都能够调用它的任意一个方法；这种动态获 取信息 以及动态调用对象方法的功能成为 Java反射

​		获取 Class 对象的 3 种方法 ： 

​		**调用某个对象的 getClass()方法：** Person p=new Person(); Class clazz=p.getClass(); 

​		**调用某个类的 class 属性**来获取该类对应的 Class 对象 Class clazz=Person.class; 

​		**使用 Class 类中的 forName()**静态方法(最安全/性能最好) Class clazz=Class.forName("类的全路径"); 

##### 	<font color="red">25、算法了解过吗？冒泡排序、选择排序、快排原理？</font>

##### 	<font color="red">26、JDK1.8的新特性有哪些?(lamda表达式、stream流、函数式接口、接口中默认方法、方法引用等等)</font>

​	**1、Lambda 表达式** ：Lambda 允许把函数作为一个方法的参数。

​	**2、方法引用**：方法引用允许直接引用已有 Java 类或对象的方法或构造方法

​	**3、函数式接口**：有且仅有一个抽象方法的接口叫做函数式接口，函数式接口可以被隐式转换为 Lambda 表达式。通常函数式接口上会添加@FunctionalInterface 注解。

​	**4、接口允许定义默认方法和静态方法**：从 JDK8 开始，允许接口中存在一个或多个默认非抽象方法和静态方法。

​	**5、Stream API**：新添加的 Stream API（java.util.stream）把真正的函数式编程风格引入到 Java 中。这种风格将要处理的元素集 合看作一种流，流在管道中传输，并且可以在管道的节点上进行处理，比如筛选， 排序，聚合等。

​	**6、日期/时间类改进**：之前的 JDK 自带的日期处理类非常不方便，我们处理的时候经常是使用的第三方 工具包，比如 commons-lang 包等。不过 JDK8 出现之后这个改观了很多，比如日期时间的创建、比较、调整、 格式化、时间间隔等。 这些类都在 java.time 包下，LocalDate/LocalTime/LocalDateTime

​	**7、Optional 类**：Optional 类是一个可以为 null 的容器对象。如果值存在则 isPresent()方法会返 回 true，调用 get()方法会返回该对象

​	**8、Java8 Base64实现**：Java 8 内置了 Base64 编码的编码器和解码器

##### 	<font color="red">27、IO流体系</font>

​	

##### 	<font color="red">28、如何实现分布式主键自增？</font>

​		1、UUID，因为UUID有部分是时间戳，所以总体上是自增的

​		2、雪花算法

​		3、Mysql主键自增，根据数据库设置自增步长

##### 	<font color="red">29、http底层，和https的区别？</font>

​		**HTTP**（HyperText Transfer Protocol：超文本传输协议）是一种用于分布式、协作式和超媒体信息系统的应用层协议。 简单来说就是一种发布和接收 HTML 页面的方法，被用于在 Web 浏览器和网站服务器之间传递信息。

​		**HTTPS**（Hypertext Transfer Protocol Secure：超文本传输安全协议）是一种透过计算机网络进行安全通信的传输协议。HTTPS 经由 HTTP 进行通信，但利用 SSL/TLS 来加密数据包。HTTPS 开发的主要目的，是提供对网站服务器的身份认证，保护交换数据的隐私与完整性。

##### <font color="red">30、 Stream？</font>

```
filter：过滤流中的某些元素
limit skip distinct sorted 都是有状态操作，这些操作只有拿到前面处理后的所有元素之后才能继续下去。
limit(n)：获取前n个元素
skip(n)：跳过前n元素，配合limit(n)可实现分页
distinct：通过流中元素的 hashCode() 和 equals() 去除重复元素
map：接收一个函数作为参数，该函数会被应用到每个元素上，并将其映射成一个新的元素。
flatMap：接收一个函数作为参数，将流中的每个值都换成另一个流，然后把所有流连接成一个流。
sorted()：自然排序，流中元素需实现Comparable接口
sorted(Comparator com)：定制排序，自定义Comparator排序器
allmatch，noneMatch，anyMatch用于对集合中对象的某一个属性值进行判断，
allMatch全部符合该条件返回true，
noneMatch全部不符合该断言返回true
anyMatch 任意一个元素符合该断言返回true
findFirst：返回流中第一个元素
findAny：返回流中的任意元素
count：返回流中元素的总个数
max：返回流中元素最大值
min：返回流中元素最小值
```



# 二、JVM

##### 	<font color="red">1、JDK和JRE的区别是什么？</font>

​		JDK:java Development Kit 的简称，java开发工具包，提供了Java的开发环境和运行环境。

​		JRE:java Runtime Environment的简称，Java运行环境，为Java的运行提供了所需环境。

​		具体来说JDK其实就包含了JRE，同时还包含了编译Java源码的编译器javac，还包含了很多Java程序调试和分析工具。

##### 	<font color="red">2、JVM的内存模型描述下？</font>

​		分为4块区域分别是：栈、程序计数器、堆、JDK1.7常量池(JDK1.8元空间)

​		**栈（线程私有）**

​		Java 虚拟机栈（局部变量表、操作数栈、动态链接、方法出口）：线程私有的(每个线程都有一个自己的 Java 虚拟机栈). 一个方法运行, 就会给这个方法创 建一个栈帧,存放局部变量， 栈帧入栈执行代码, 执行完毕之后出栈(弹栈)存引用变量，基本数据类型

​		本地方法栈：线程私有的(每个线程都有一个自己的本地方法栈), 和 Java 虚拟机栈类似, Java 虚拟机栈 加载的是普通方法,本地方法加载的是 native 修饰的方法. native:在 java 中有用 native 修饰的,表示这个方法不是 java 原生的

​		**程序计数器（线程私有）**

​		线程私有的(每个线程都有一个自己的程序计数器), 是一个指针. 代码运行, 执行命令. 而 每个命令都是有行号的,会使用程序计数器来记录命令执行到多少行了.记录下一行运行代码的内存地址。设计程序计数器的原因是因为多线程，线程间的切换

​		**堆（线程共享）**

​		线程共享的(所有的线程共享一份). 存放对象的,new 的对象都存储在这个区域.还有就是 常量池。

​		**方法区（常量池、元空间）**

​		 存储.class 信息, 类的信息,方法的定义,静态变量等.而常量池放到堆里存储 JDK1.8 和 JDK1.7 的 jvm 内存最大的区别是, 在 1.8 中方法区是由元空间(元数据区)来实 现的, 常量池. 1.8 不存在方法区,将方法区的实现给去掉了.而是在本地内存中,新加入元数据区(元空间)

##### 	<font color="red">3、JVM双亲委派加载机制，为什么JVM这么做？有违反双亲委派的例子吗？</font>

​		**双亲委派加载机制：**如果一个类加载器收到了加载某个类的请求,则该类加载器并不会去加载该类,而是把这个请求委派给父类加载器,每一个层次的类加载器都是如此,因此所有的类加载请求最终都会传送到顶端的启动类加载器;只有当父类加载器在其搜索范围内无法找到所需的类,并将该结果反馈给子类加载器,子类加载器会尝试去自己加载。

​		双亲委派机制保证了Java程序的稳定运行，可以**避免类的重复加载**，也保证了**Java的核心API不被篡改**。如果有人想替换系统级别的类：String.java，篡改它的实现。在这种机制下这些系统的类已经被BootstrapclassLoader加载过了，所以并不会再去加载。

​		以**Driver**接口为例，由于Driver接口定义在jdk当中的，而其实现由各个数据库的服务商来提供，比如mysql的就写了MySQL Connector，那么问题就来了，DriverManager（也由jdk提供）要加载各个实现了Driver接口的实现类，然后进行管理，但是DriverManager由启动类加载器加载，只能加载JAVA_HOME的lib下文件，而其实现是由服务商提供的，由系统类加载器加载，这个时候就需要启动类加载器来委托子类来加载Driver实现，从而破坏了双亲委派，

##### 	<font color="red">4、类的加载流程是什么样的，每个阶段解释一下</font>

​		类加载过程主要分为七个阶段：加载、验证、准备、解析、初始化、使用、卸载。

​		**加载：**

​			1）、通过一个类的全限定名加载该类对应的二进制字节流。主要通过类加载器实现。

​			2）、将字节流所代表的静态存储结构转化为方法区的运行时数据结构。

​			3）、在内存中生成一个代表这个类的java.lang.Class对象，作为方法区各个类访问该类的入口。（Hotspot 在方法区生成该类）。

​		**验证：**

​			1）、文件格式验证：验证类文件的版本号常量等是否符合当前虚拟机支持的范围。

​			2）、元数据验证：验证类的语义信息，是否符合java语言规范的要求。

​			3）、字节码验证：验证程序语义是合法的、合乎规范的。主要通过stackmapframe结构。

​			4）、符号引用验证：虚拟机在将符号引用转化为直接引用，验证符号引用全限定名代表的类是否能够找到，对应的域和方法是否能找到，访问权限是否合法。

​		**准备：**准备阶段主要是将类变量（被static修饰符修饰）在方法区进行内存分配并进行初始化。

​		**解析：**

​			1）、类或接口解析：将符合引用转化为类的直接引用，并检查访问权限。

​			2）、字段解析：将字段的符号引用转化为字段所属的类信息或其父类该字段的直接引用，并检查访问权限。

​			3）、类方法解析：将类方法的符号引用转化为类方法所属的类信息或其父类该字段的直接引用，并检查访问权限。

​			4）、接口方法解析：将接口方法的符号引用转化为接口方法所属的接口信息或其父类该字段的直接引用，并检查访问权限。

​		**初始化：**初始化阶段编译器会将类文件声明的静态赋值变量和静态区域合并生成<cinit>方法并进行调用。

##### 	<font color="red">5、JVM的GC的主要区域以及各自的GC机制是什么样的？</font>

​		主要区域是堆，堆分为新生代和老年代，新生代基本采用复制算法，老年代采用标记整理算法。

##### 	<font color="red">6、JVM的GC算法都有哪些？</font>

​		**标记-清除算法：**标记无用对象，然后进行清除回收。**缺点：**效率不高，无法清除垃圾碎片。

​		**标记-整理算法：**标记无用的对象，让所有存活的对象都向一端移动，然后直接清除掉端边界以外的内存。

​		**复制算法：**按照容量划分两个相等的内存区域，当一块用完的时候将活着的对象复制到另一块上，然后再把已使用的内存空间一次清理掉。**缺点：**内存使用率不高，只有原来的一半。

​		**分代算法：**根据对象存活周期的不同将内存划分为几块，一般是新生代和老年代，新生代基本采用复制算法，老年代采用标记整理算法，	

##### 	<font color="red">7、JVM监控工具（两种）</font>

1.JDK自带的工具:

**[jconsole]:**这是一款基于JMX的GUI性能监测工具，从JDK1.5开始加入。它可以用于查看应用程序的运行概况、内存、线程、类、VM概括、MBean等信息。jconsole提供了一个概览图和主要的功能板块，如概述、内存、线程、类、VM、MBean等，方便用户监控和分析JVM的运行状态。

**[jvisualvm]:**这也是一款免费的Java虚拟机监视、分析和调试工具，从JDK1.6开始加入。jvisualvm能够监控服务的CPU、内存、线程、类等信息，并支持远程连接JVM。它提供了一个丰富的用户界面，包括概述、监视、线程、抽样器等板块，并且支持插件安装，使得用户可以根据需要安装特定的监控插件。

**2.阿里的Arthas:**Arthas是阿里巴巴开源的Java诊断工具，它以命令行的方式提供了丰富的功能，能够实时监控和诊断Java应用的运行状态，帮助开发者快速定位和解决性能问题。Arthas可以在生产环境中使用，而不需要对应用进行任何修改.

Arthas具有以下几个显著的特点：

**无侵入性：**Arthas不需要对应用代码进行任何修改，可以在运行时动态注入和监控应用。
**实时性：**Arthas提供实时的监控和诊断能力，可以对应用进行实时的性能分析和问题定位。
**丰富的功能：**Arthas提供了丰富的功能，包括方法追踪、性能分析、内存分析、线程分析等，满足不同场景下的调优需求。



##### 	<font color="red">8、垃圾回收器</font>

​	新生代回收器：Serial、ParNew、Parallel Scavenge

​	老年代回收器：Serial Old、Parallel Old、CMS

​	整堆回收器：G1

**串行垃圾回收器（Serial）**：它为单线程环境设计并且只使用一个线程进行垃圾回收，会暂停所有的用户线程。所以不适合服务器环境。

**并行垃圾回收器（Parallel）**：多个垃圾回收线程并行工作，此时用户线程是暂停的，适用于科学计算/大数据处理等弱交互场景。

**并发垃圾回收器（CMS）**：用户线程和垃圾收集线程同时执行（不一定是并行，可能交替执行），不需要停顿用户线程。互联网公司多用它，适用于对响应时间有要求的场景。

**G1垃圾回收器**：G1垃圾回收器将堆内存分割成不同的区域然后并发的对其进行垃圾回收。

**时代历程**

第一阶段：单线程收集时代（Serial和Serial Old）

第二阶段：多线程收集时代（Parallel Scanvenge 和Parallel Old）

第三阶段：并发收集时代（ParNew和CMS）

第四阶段：智能并发收集时代（G1）

**常用组合：**Serial+Serial Old， Parallel Scavenge+Parallel Old，ParNew+CMS，G1（不需要组合其他收集器）。

##### <font color="red">8、JVM调优</font>

​		jvm调优涉及到两个很重要的概念：吞吐量和响应时间。jvm调优主要是针对他们进行调整优化，达到一个理想的目标，根据业务确定目标是吞吐量优先还是响应时间优先。

​	**吞吐量：**用户代码执行时间/(用户代码执行时间+GC执行时间)。

​	**响应时间：**整个接口的响应时间(用户代码执行时间+GC执行时间)，stw时间越短，响应时间越短。

​		 调优的前提是熟悉业务场景，先判断出当前业务场景是吞吐量优先还是响应时间优先。调优需要建立在监控之上，由压力测试来判断是否达到业务要求和性能要求。调优的步骤大致可以分为：

​		1、熟悉业务场景，了解当前业务系统的要求，是吞吐量优先还是响应时间优先；

​		2、选择合适的垃圾回收器组合，如果是吞吐量优先，则选择ps+po（Parallel Scavenge并行清除加Parallel Old）组合；如果是响应时间优先，在1.8以后选择G1，在1.8之前选择ParNew+CMS组合；

​		3、规划内存需求，只能进行大致的规划。

​		4、CPU选择，在预算之内性能越高越好；

​		5、根据实际情况设置升级年龄，最大年龄为15；

​		6.设定日志参数：-Xloggc:/path/name-gc-%t.log -XX:+UseGCLogFileRotation -XX:NumberOfGCLogs=5 -XX:GCLogFileSize=20M -XX:+PrintGCDetails -XX:+PrintGCDateStamps -XX:+PrintGCCauses

    -XX:+UseGCLogFileRotation：GC文件循环使用
    -XX:NumberOfGCLogs=5：使用5个GC文件
    -XX:GCLogFileSize=20M：每个GC文件的大小
    -Xmx3550m：设置 JVM 最大可用内存为 3550M。
    -Xms3550m：设置 JVM 初始内存为 3550m。注意：此值一般设置成和-Xmx 相同，以避免每次垃圾回收完成后 JVM 重新分配内存。
    -Xmn2g：设置年轻代大小为 2G。整个 JVM 内存大小=年轻代大小 + 年老代大小 +持久代大小。此值对系统性能影响较大，Sun 官方推荐配置为整个堆的 3/8。
    -Xss256k：设置每个线程的栈大小。JDK5.0 以后每个线程栈大小为 1M，以前每个线程栈大小为 256K。根据应用的线程所需内存大小进行调整。在相同物理内存下，减小这个值能生成更多的线程。
    -XX:NewRatio=4:设置年轻代（包括 Eden 和两个 Survivor 区）与年老代的比值（除去持久代）。设置为 4，则年轻代与年老代所占比值为 1:4。（该值默认为 2）
    -XX:SurvivorRatio=4：设置年轻代中 Eden 区与 Survivor 区的大小比值。设置为 4，则两个 Survivor 区与一个 Eden 区的比值为 2:4 
上面这三个参数放在一起代表的含义是：5个GC文件循环使用，每个GC文件20M，总共使用100M存储日志文件，当5个GC文件都使用完毕以后，覆盖第一个GC日志文件，生成新的GC文件。

##### <font color="red">9、CPU使用率飙高问题</font>

​		当cpu经常飙升到100%的使用率，那么证明有线程长时间占用系统资源不进行释放，需要定位到具体是哪个线程在占用，定位问题的步骤如下(linux系统)：

​		1、使用top命令常看当前服务器中所有进程（jps命令可以查看当前服务器运行java进程）,找到当前cpu使用率最高的进程，获取到对应的pid（进程识别号）；

​		 2、然后使用top -Hp pid，查看该进程中的各个线程信息的cpu使用，找到占用cpu高的线程pid；

​		3.使用jstack pid打印它的线程信息，需要注意的是，通过jstack命令打印的线程号和通过top -Hp打印的线程号进制不一样，需要进行转换才能进行匹配，jstack中的线程号为16进制，而top -Hp打印的是10进制。

​		4、使用jastack命令分析线程信息的时候需要关注线程对应的运行状态：

 			runnable代表当前线程正在运行，waiting代表当前线程正在等待，该状态需要进行特殊关注wait fot 后面的线程号，因为如果当前处于waiting状态的程序长时间处于等待状态，那么就需要知道它在等待哪个线程结束，也就是wait for后面的线程号(jdk版本不同，单词可能不一样，总之就是在日志中找到它等待的线程号)然后根据线程号找到对应的线程，去查看当前线程有什么问题。

##### <font color="red">10、内存标高问题</font>

​	 内存飙高一般都是堆中对象无法回收造成，因为java中的对象大部分存储在堆内存中。其实也就是常见的oom问题(Out Of Memory)。

​	 1、jinfo pid，可以查看当前进行虚拟机的相关信息列举出来；

 	2、jstat -gc pid ms，多长毫秒打印一次gc信息，打印信息如下，里面包含gc测试，年轻代/老年带gc信息等；

​	3、jmap -histo pid | head -20，查找当前进程堆中的对象信息，加上管道符后面的信息以后，代表查询对象数量最多的20个：

​	4、 jmap -dump:format=b,file=xxx pid，可以生成堆信息的文件，但是这个命令不建议在生产环境使用，因为当内存较大时，执行该命令会占用大量系统资源，甚至造成卡顿。建议在项目启动时添加下面的命令，在发生oom时自动生成堆信息文件：-XX:+HeapDumpOnOutOfMemory。如果需要在线上进行堆信息分析，如果当前服务存在多个节点，可以下线一个节点，生成堆信息，或者使用第三方工具，阿里的arthas。

##### <font color="red">11、怎么观察出线上问题的？</font>

1、压测的时候通过图形工具进行观察

2、项目有多台机器，下线一个节点，在这个节点上生成堆信息

3、请求特别多，使用tcpdump将请求复制一份到测试机上面，在测试机上面观察；

##### <font color="red">12、GC的时候为什么要加STW(Stop-The-World)</font>

1.停止当前线程的原因是因为当前线程的工作可能会让GC线程分不清哪些是要回收的垃圾



# 三、Spring & SpringBoot

##### 	<font color="red">1、说下对SpringIOC的理解，怎么理解控制反转？ </font>

​		 **IOC** 的意思是**控制反转**，是指创建对象的**控制权的转移**，以前创建对象的主动权和 时机是由自己把控的，而现在这种权力转移到 Spring 容器中，并由容器根据配置文件去创 建实例和管理各个实例之间的依赖关系，对象与对象之间松散耦合，也利于功能的复用。最直观的表达就是，IOC 让对象的创建不用去 new 了，可以由 spring 根据我们提供的配置文 件自动生产，我们需要对象的时候，直接从 Spring 容器中获取即可. 

​		Spring 的配置文件中配置了类的字节码位置及信息, 容器生成的时候加载配置文件识 别字节码信息, 通过反射创建类的对象. 

​		Spring 的 IOC 有三种注入方式 ：构造器注入, setter 方法注入, 根据注解注入。

##### 	<font color="red">2、Spring如何解决IOC中的循环依赖问题？</font>

​		1、A创建过程中先实例化，然后将自己放到第三级缓存里面，然后填充属性，发现需要B，但是B在所有的缓存中都不存在，于是A，去实例化B

​		2、B实例化，然后填充属性的时候发现又需要A，于是B先查一级缓存，没有A，再查二级缓存，还是没有A，再查三级缓存，找到了A，然后把三级缓存里面的这个A放到二级缓存里面，删除三级缓存里面的A，把A赋给了B中的A引用

​		3、B顺利初始化完毕，将自己放到一级缓存里面（此时B里面的A依然是创建中状态）然后回来接着创建A，由于此时B已经创建结束，直接从一级缓存里面拿到成品B，完成创建，并将A放到一级缓存中，删除二级缓存中的A。

##### 	<font color="red">3、说下对SpringAOP的理解、有哪些通知？使用场景有哪些？（底层原理：两种动态代理）</font>

​		**AOP：**一般称为面向切面编程，作为面向对象的一种补充，用于将那些与业务无关， 但却对多个对象产生影响的公共行为和逻辑，抽取并封装为一个可重用的模块，这个模块被 命名为“切面”（Aspect）. SpringAOP 使用的动态代理，所谓的动态代理就是说 AOP 框 架不会去修改字节码，而是每次运行时在内存中临时为方法生成一个 AOP 对象，这个 AOP 对象包含了目标对象的全部方法，并且在特定的切点做了增强处理，并回调原对象的方法。

​		一共有5种通知

​			**前置通知[]before]**：在切点运行之前执行 

​			**后置通知[after-returning]**：在切点正常结束之后执行 

​			**异常通知[after-throwing]**：在切点发生异常的时候执行 

​			**最终通知[after]**：在切点的最终执行 

​			Spring 还有一种特殊的通知,叫做**环绕通知**

执行顺序

- ①环绕通知：@Around
- ②前置通知：@Before
- ③执行连接点方法
- ④环绕通知：@Around
- ⑤后置通知：@After
- ⑥正常返回通知：@AfterReturning，如果发生异常那么就是异常通知@AfterThrowing

​		使用场景：

​			记录日志、自定义缓存、接口数据鉴权、性能监控、事务管理、实现防止表单重复提交

##### 	<font color="red">4、Java实现动态代理有哪些方式？区别是什么？</font>

​		(1)**JDK 动态代理**只提供接口代理，不支持类代理，核心 InvocationHandler 接口和 Proxy 类，InvocationHandler 通过 invoke()方法反射来调用目标类中的代码，动态地将 横切逻辑和业务编织在一起，Proxy 利用 InvocationHandler 动态创建一个符合某一接口 的的实例, 生成目标类的代理对象。

​		 (2) **CGLIB：**如果代理类没有实现 InvocationHandler 接口，那么 Spring AOP 会选择使用 CGLIB 来动态代理目标类。CGLIB（Code Generation Library），是一个代码生成的类库， 可以在运行时动态的生成指定类的一个子类对象，并覆盖其中特定方法并添加增强代码，从 而实现 AOP。CGLIB 是通过继承的方式做的动态代理，因此如果某个类被标记为 final， 那么它是无法使用 CGLIB 做动态代理的

##### 	<font color="red">5、对Spring声明式事务的理解？Spring的事务隔离级别？Spring事务传播行为？</font>

​		声明式事务：通过打注解的方式去声明一下即可：@Transactional
​		编程式事务：开启事务、提交、回滚都是需要自己编写代码的

​		隔离级别：Rrad Uncommitted(读未提交)、Read committed(读已提交/不可重复读)、repeatable read(可重复读)、Serializable(串行化)

​		传播行为：

​			1.Propagation.REQUIRED  ：（默认）如果当前没有事务，就新建一个事务，如果已经存在一个事务中，加入到这个事务中。

​			2.Propagation.SUPPORTS：表示当前方法不需要事务上下文，但是如果存在当前事务的话，那么这个方法会在这个事务中运行

​			3.Propagation.MANDATORY：表示该方法必须在事务中运行，如果当前事务不存在，则会抛出一个异常。不会主动开启一个事务。

​			4.Propagation.REQUIRES_NEW：表示当前方法必须运行在它自己的事务中。一个新的事务将被启动，如果存在当前事务，在该方法执行期间，当前事务会被挂起(如果一个事务已经存在，则先将这个存在的事务挂起)。如果使用JTATransactionManager的话，则需要访问TransactionManager。

​			5.Propagation.NOT_SUPPORTED：表示该方法不应该运行在事务中，如果存在当前事务，在该方法运行期间，当前事务将被挂起。如果使用JTATransactionManager的话，则需要访问TransactionManager。

​			6.Propagation.NOT_SUPPORTED：表示当前方法不应该运行在事务上下文中，如果当前正有一个事务在运行，则会抛出异常。

​			7.Propagation.NESTED：表示如果当前已经存在一个事务，那么该方法将会在嵌套事务中运行。嵌套的事务可以独立于当前事务进行单独地提交或回滚。如果当前事务不存在，那么其行为与REQUIRED一样。嵌套事务一个非常重要的概念就是内层事务依赖于外层事务。外层事务失败时，会回滚内层事务所做的动作。而内层事务操作失败并不会引起外层事务的回滚。

##### 	<font color="red">6、什么情况下会让spring事务失效</font>

​		**2、没有被 Spring 管理：**

​		**3、方法不是 public 的：** **@Transactional** 只能用于 public 的方法上，否则事务会失效，如果要用在非 public 方法上，可以开启 AspectJ 代理模式。

​		**4、方法内部调用：**在同一个类中的方法直接内部调用，会导致事务失效。解决办法：在该Service类中注入自己也是一种选择。aopcontext方法

​		**5、方法用final修饰：**spring事务底层使用了aop，也就是通过jdk动态代理或者cglib，帮我们生成了代理类，在代理类中实现的事务功能。但如果某个方法用final修饰了，那么在它的代理类中，就无法重写该方法，从而实现事务功能。

​		**6、异常被吃了：**因为开发者自己捕获了异常，又没有手动抛出，换句话说就是把异常吞掉了。

如果想要spring事务能够正常回滚，必须抛出它能够处理的异常。如果没有抛异常，则spring认为程序是正常的。

​		**7、手动抛了别的异常：**因为spring事务，默认情况下只会回滚RuntimeException（运行时异常）和Error（错误），对于普通的Exception（非运行时异常），它不会回滚。

##### 	<font color="red">7、Spring有哪些核心注解？分别的作用？</font>

​		1、@Component(任何层) @Controller @Service @Repository（dao）: 用于 实例化对象 

​		2、@Scope : 设置 Spring 对象的作用域 

​		3、@PostConstruct @PreDestroy : 用于设置 Spring 创建对象在对象创建之后和销 毁之前要执行的方法 

​		4、@Value: 简单属性的依赖注入 

​		5、@Autowired: 对象属性的依赖注入 

​		6、@Qualifier: 要和@Autowired 联合使用，代表在按照类型匹配的基础上，再按照 名称匹配。 

​		7、@Resource 按照属性名称依赖注入 

​		8、@ComponentScan: 组件扫描 

​		9、@Bean: 表在方法上,用于将方法的返回值对象放入容器 

​		10、@PropertySource: 用于引入其它的 properties 配置文件 

​		11、@Import: 在一个配置类中导入其它配置类的内容 

​		12、@Configuration: 被此注解标注的类,会被 Spring 认为是配置类。Spring 在启动 的时候会自动扫描并加载所有配置类，然后将配置 类中 bean 放入容器 

​		13、@Transactional 此注解可以标在类上，也可以表在方法上，表示当前类中的方法 具有事务管理功能。

##### 	<font color="red">8、Spring和SpringBoot的关系？</font>

​		Spring Boot](https://github.com/spring-projects/spring-boot) 是 Spring 的**子项目**、脚手架，正如其名字，提供 Spring 的引导( **Boot** )的功能。

##### <font color="red">8.5、Spring Boot 的约定优于配置，你的理解是什么？</font>

我从 4 个点方面来回答。 

1. 首先， 约定优于配置是一种软件设计的范式，它的核心思想是减少软件开发人员 对于配置项的维护，从而让开发人员更加聚焦在业务逻辑上。 

2. Spring Boot 就是约定优于配置这一理念下的产物，它类似于 Spring 框架下的一 个脚手架，通过 Spring Boot，我们可以快速开发基于 Spring 生态下的应用程序。 

3. 基于传统的 Spring 框架开发 web 应用，我们需要做很多和业务开发无关并且只需 要做一次的配置，比如 

   ​	a. 管理 jar 包依赖 

   ​	b. web.xml 维护

   ​	c. Dispatch-Servlet.xml 配置项维

   ​	d. 应用部署到 Web 容器 

   ​	e. 第三方组件集成到 Spring IOC 容器中的配置项维护 而在 Spring Boot 中，我们不需要再去做这些繁琐的配置，Spring Boot 已经自动帮我 们完成了，这就是约定由于配置思想的体现。

   4.Spring Boot 约定由于配置的体现有很多，比如 

   ​	a. Spring Boot Starter 启动依赖，它能帮我们管理所有 jar 包版本 

   ​	b. 如果当前应用依赖了 spring mvc 相关的 jar，那么 Spring Boot 会自动内置 Tomcat 容器来运行 web 应用，我们不需要再去单独做应用部署。 

   ​	c. Spring Boot 的自动装配机制的实现中，通过扫描约定路径下的 spring.factories 文件来识别配置类，实现 Bean 的自动装配。 	d. 默认加载的配置文件 application.properties 等等。 总的来说，约定优于配置是一个比较常见的软件设计思想，它的核心本质都是为了更高 效以及更便捷的实现软件系统的开发和维护。 

   以上就是我对这个问题的理解。

##### 	<font color="red">9、SpringBoot的自动装配原理是什么？</font>

​		**@SpringBootApplication**为springboot核心注解，也是springboot完成**自动配置的核心**所在，本身包含如下注解：				

​				1、**@ComponentScan** ： **扫描当前包及子包下**所有被 @Component、@Controller、@Service、@Repositore注解所标注的类并**纳入spring容器**中

​				2、**@SpringBootConfiguration** ： 其本质就是**@Configuration**，标注表示**该类是一个配置类**，可将其中被**@Bean所标注的方法实例化**并**纳入spring容器**中

​				3、**@EnableAutoConfiguration**  该注解也是一个复合注解，是SpringBoot能完成**自动配置**的**核心注解**，它主要流程包括：

​						a、**@AutoConfigurationPackage**(配合@componentScan注解返回了当前主程序类的 同级以及子级的包组件)

​						b、借助**@Import注解**加载(**AutoConfigurationImportSelector.class**)

​						这个主要作用就是调用**selectImport**方法且借助**SpringfactoresLoader**去解析classpath下的**spring.factores**文件，将其中以**org.springfremwork.boot.autoconfigure.EnabelAutoConfiguration**为**key**对应的**value**加载进**cach**,这个**value**其实就是**希望纳入到spring容器的特殊实例类名**，也就是**pom文件的各种starter、jar**，之后再将其**实例化**并**加载到spring容器**中

##### 	<font color="red">10、SpringBoot的核心注解是哪个？详细说下</font>

​		启动类上面的注解是@SpringBootApplication，它也是Spring Boot的核心注解，主要组合包含了以下3个注解：

​		1、@SpringBootConfiguration：组合了 @Configuration 注解，实现配置文件的功能。

​		2、@EnableAutoConfiguration：打开自动配置的功能，也可以关闭某个自动配置的选项。

如关闭数据源自动配置功能： @SpringBootApplication(exclude = { DataSourceAutoConfiguration.class })。

​		3、@ComponentScan：Spring组件扫描。

##### 	<font color="red">11、SpringBoot项目的启动加载流程大概说下</font>

​	

##### <font color="red">12、Spring Boot 配置文件加载顺序？</font>

​			文件夹读取优先级：file:./config/ >  file:./  > classpath:/config/  >  classpath:/

​			文件名优先级：application > application-default

​			文件名类型优先级：application.properties > application.xml > application.yml > application.yaml 

##### 	<font color="red">13、SpringBoot项目读取配置文件的方式有几种？</font>

​		Spring Boot 目前支持 **2** 种读取配置：

1. `@Value` 注解，读取配置到属性。最最最常用。另外，支持和 `@PropertySource` 注解一起使用，指定使用的配置文件。

2. `@ConfigurationProperties` 注解，读取配置到类上。另外，支持和 `@PropertySource` 注解一起使用，指定使用的配置文件。

##### 	<font color="red">14、如何自定义SpringBoot starter？</font>

​			Spring Starter的作用：

​			在我们的日常开发工作中，经常会有一些独立于业务之外的配置模块，我们经常将其放到一个特定的包下，然后如果另一个工程需要复用这块功能的时候，需要将代码硬拷贝到另一个工程，重新集成一遍，麻烦至极。如果我们将这些可独立于业务代码之外的功配置模块封装成一个个starter，复用的时候只需要将其在pom中引用依赖即可，SpringBoot为我们完成自动装配。

​		步骤：

​				a、给提供复用代码的所在模块命名，命名规则为`xxx-spring-boot-starter`，以区分这是我们自定义的starter

​				b、将提供复用代码的服务类通过config类@Bean的方式进行创建

​				c、打开META-INF下的spring.factories，将config路径配置在org.springframework.boot.autoconfigure.EnableAutoConfiguration的value中，如：

```yaml
org.springframework.boot.autoconfigure.EnableAutoConfiguration=com.demo.starter.config.DemoConfig
```

​				d、使用：在其他模块添加starter依赖，如：	

```xml
	 <dependency>
          <groupId>com.demo</groupId>
          <artifactId>demo-spring-boot-starter</artifactId>
          <version>0.0.1-RELEASE</version>
     </dependency>
```

##### 	<font color="red">15、BeanFactory和FactoryBean的区别？</font>

​		 **BeanFactory 以Factory结尾，表示它是一个工厂类，用于管理Bean的一个工厂在Spring中，所有的Bean都是由BeanFactory(也就是IOC容器)来进行管理的。** BeanFactory定义了IOC容器的最基本形式，并提供了IOC容器应遵守的的最基本的接口，也就是Spring IOC所遵守的最底层和最基本的编程规范。它的职责包括：实例化、定位、配置应用程序中的对象及建立这些对象间的依赖。在Spring代码中，BeanFactory只是个接口，并不是IOC容器的具体实现，但是Spring容器给出了很多种实现，如 DefaultListableBeanFactory、XmlBeanFactory、ApplicationContext等，都是附加了某种功能的实现。

​		 **但对FactoryBean而言，这个Bean不是简单的Bean，而是一个能生产或者修饰对象生成的工厂Bean,它的实现与设计模式中的工厂模式和修饰器模式类似。**一般情况下，Spring通过反射机制利用<bean>的class属性指定实现类实例化Bean，在某些情况下，实例化Bean过程比较复杂，如果按照传统的方式，则需要在<bean>中提供大量的配置信息。配置方式的灵活性是受限的，这时采用编码的方式可能会得到一个简单的方案。

​		Spring为此提供了一个org.springframework.bean.factory.FactoryBean的工厂类接口，用户可以通过实现该接口定制实例化Bean的逻辑。FactoryBean接口对于Spring框架来说占用重要的地位，Spring自身就提供了70多个FactoryBean的实现。它们隐藏了实例化一些复杂Bean的细节，给上层应用带来了便利。从Spring3.0开始，FactoryBean开始支持泛型，即接口声明改为FactoryBean<T>的形式

##### 	<font color="red">16、Spring Bean的生命周期是什么？</font>

```
一、入口：进入AbstractBeanFactory.doGetBean()方法
	1、通过getSingleton(beanName)方法逐级从三级缓存中去拿，此时是初始化，显然拿不到，如果拿到，直接返回：如果拿不到，走下面的创建逻辑
	2、doCreateBean（主要做了四件事）
		1)、通过createBeanInstance() 执行Bean的构造器方法实例化对象（堆内存创建了一片空间）
		2)、通过addSingletonFactory() 将已完成实例化，但是未完成属性赋值和初始化的一个不完整bean添加到【三级缓存中】
		3)、属性填充赋值&依赖注入（populateBean：填充依赖的每个属性，其实就是套娃，从一开始重复整个流程）
		4)、初始化（initializeBean）
			1、执行Bean Aware系列接口（前提：该bean实现了这些Aware接口）
			2、执行初始化前的处置操作
				ApplicationContextAware.setApplicationContext（可以被拓展的）
				@PostConstruct
			3、执行：InitializingBean.afterPropertiesSet
			4、执行初始化之后的处置操作（其中就有非循环依赖要产生的动态代理对象）
	3、把成品Bean放入到一级缓存，并删除二、三级缓存
```

​		1、实例化一个 Bean，也就是我们通常说的 new 

​		2、 按照 Spring 上下文对实例化的 Bean 进行配置，也就是 IOC 注入 47 

​		3、如果这个 Bean 实现 dao 了 BeanNameAware 接口，会调用它实现的 setBeanName(String beanId)方法，此处传递的是 Spring 配置文件中 Bean 的 ID 

​		4、如果这个 Bean 实现了 BeanFactoryAware 接口，会调用它实现的 setBeanFactory()， 传递的是 Spring 工厂本身（可以用这个方法获取到其他 Bean） 

​		5、 如果这个 Bean 实现了 ApplicationContextAware 接口，会调用 setApplicationContext(ApplicationContext)方法，传入 Spring 上下文，该方式同样可 以实现步骤 4，但比 4 更好，以为 ApplicationContext 是 BeanFactory 的子接口，有更多 的实现方法 

​		6、 如果这个 Bean 关联了 BeanPostProcessor 接口，将会调用 postProcessBeforeInitialization(Object obj, String s)方法，BeanPostProcessor 经常被 用作是 Bean 内容的更改，并且由于这个是在 Bean 初始化结束时调用 After 方法，也可用 于内存或缓存技术 

​		7、如果这个 Bean在 Spring 配置文件中配置了 init-method 属性会自动调用其配置的初始 化方法 

​		8、如果这个 Bean 关联了 BeanPostProcessor 接口，将会调用 postAfterInitialization(Object obj, String s)方法 注意：以上工作完成以后就可以用这个 Bean 了，那这个 Bean 是一个 single 的，所以 一般情况下我们调用同一个 ID 的 Bean 会是在内容地址相同的实例 

​		9、 当 Bean 不再需要时，会经过清理阶段，如果 Bean 实现了 DisposableBean 接口，会 调用其实现的 destroy 方法 

​		10、 最后，如果这个 Bean 的 Spring 配置中配置了 destroy-method 属性，会自动调用其 配置的销毁方法

##### <font color="red">17、SpringBoot性能监控？</font>

​	SpringBoot提供了监控工具其中包括（应用程序健康状况、应用程序性能指标、应用程序日志输出）Spring Boot 的监控功能非常易于使用。只需要在 <code>pom.xml</code> 文件中添加以下依赖：

```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
```

**应用程序健康状况**

Spring Boot 提供了 <code>/actuator/health</code> 端点，用于检查应用程序的健康状况。该端点返回一个 JSON 格式的响应，包含了应用程序的健康状态。如果应用程序正常运行，该端点将返回一个 <code>{"status":"UP"}</code> 的响应

```json
$ curl localhost:8080/actuator/health
{"status":"UP"}
```

**应用程序性能指标**

Spring Boot 提供了 <code>/actuator/metrics</code> 端点，用于检查应用程序的性能指标。该端点返回一个 JSON 格式的响应，包含了应用程序的各种性能指标。例如，可以通过该端点查看应用程序的 HTTP 请求的响应时间、请求的数量等指标。

```json
$ curl localhost:8080/actuator/metrics/http.server.requests
{
  "name": "http.server.requests",
  "baseUnit": "seconds",
  "measurements": [
    {
      "statistic": "COUNT",
      "value": 18.0
    },
    {
      "statistic": "TOTAL_TIME",
      "value": 0.006175232
    },
    {
      "statistic": "MAX",
      "value": 0.001184169
    }
  ],
  "availableTags": [
    {
      "tag": "uri",
      "values": [
        "/actuator/metrics",
        "/actuator/health",
        "/favicon.ico"
      ]
    },
    {
      "tag": "outcome",
      "values": [
        "SUCCESS"
      ]
    },
    {
      "tag": "method",
      "values": [
        "GET"
      ]
    },
    {
      "tag": "status",
      "values": [
        "200"
      ]
    }
  ]
}

```

**应用程序日志输出**

Spring Boot 提供了 <code>/actuator/loggers</code> 端点，用于管理应用程序的日志输出。该端点可以返回应用程序当前所有 logger 的配置信息，并且可以修改某个 logger 的配置信息。例如，可以通过该端点修改某个 logger 的<a href="https://so.csdn.net/so/search?q=%E6%97%A5%E5%BF%97%E7%BA%A7%E5%88%AB&amp;spm=1001.2101.3001.7020" target="_blank" class="hl hl-1" data-report-click="{&quot;spm&quot;:&quot;1001.2101.3001.7020&quot;,&quot;dest&quot;:&quot;https://so.csdn.net/so/search?q=%E6%97%A5%E5%BF%97%E7%BA%A7%E5%88%AB&amp;spm=1001.2101.3001.7020&quot;,&quot;extra&quot;:&quot;{\&quot;searchword\&quot;:\&quot;日志级别\&quot;}&quot;}" data-tit="日志级别" data-pretit="日志级别">日志级别</a>。

```json
<code class="has-numbering" onclick="mdcp.signin(event)" style="position: unset;">$ curl localhost:8080/actuator/loggers/com.example
{
  "configuredLevel": "DEBUG",
  "effectiveLevel": "DEBUG"
}

$ curl -X POST localhost:8080/actuator/loggers/com.example -H 'Content-Type: application/json' -d '{"configuredLevel": "INFO"}'
{
  "configuredLevel": "INFO",
  "effectiveLevel": "INFO"
}
```

##### 	<font color="red">18、说下SpringMvc的流程（从访问一个URL到得到页面结果的具体流程：DispatcherServlet的职责流程）</font>

​		1、用户发送请求到前端控制器（DispatcherServlet） 

​		2、前 端 控 制 器 （ DispatcherServlet ） 收 到 请 求 调 用 处 理 器 映 射 器 （HandlerMapping），去查找处理器（Handler） 

​		3、处理器映射器（HandlerMapping）找到具体的处理器(可以根据 xml 配置、注解进行 查找)，生成处理器对象及处理器拦截器(如果有则生成)一并返回给前端控制器 DispatcherServlet。

​		4、 前端控制器（DispatcherServlet）调用处理器映射器（HandlerMapping）

​		 5、 处理器适配器（HandlerAdapter）去调用自定义的处理器类(Controller，也叫 后端控制器)。

​		6、自定义的处理器类(Controller，也叫后端控制器)将得到的参数进行处理并返回结 果给处理器映射器（HandlerMapping） 

​		7、处 理 器 适 配 器 （ HandlerAdapter ） 将 得 到 的 结 果 返 回 给 前 端 控 制 器 （DispatcherServlet） 

​		8、 DispatcherServlet( 前 端 控 制 器 ) 将 ModelAndView 传 给 视 图 解 析 器 (ViewReslover) 

​		9、 视图解析器(ViewReslover)将得到的参数从逻辑视图转换为物理视图并返回给 前端控制器（DispatcherServlet） 

​		10、前端控制器（DispatcherServlet）调用物理视图进行渲染并返回 

​		11、 前端控制器（DispatcherServlet）将渲染后的结果返回

# 四、Mysql & Mybatis？

##### <font color="red">0、常用sql语句？</font>

```sql
创建数据库	CREATE DATABASE 数据库名;
删除数据库	drop database <数据库名>;
创建表	CREATE TABLE table_name (column_name column_type);
删除表	DROP TABLE table_name ;
增		INSERT INTO table_name ( field1, field2,...fieldN ) VALUES( value1, value2,...valueN );
删		delete from table_name where id=1
改		update table_name set name = '张三' where id=1
查		select * from table_name where
去重查询 distinct
模糊查询重点 like
排序查询 ORDER BY  倒序DESC/正序ASC
分组查询 GROUP BY
分页查询 limit

#连接 
INNER JOIN（内连接,或等值连接）：获取两个表中字段匹配关系的记录。
LEFT JOIN（左连接）：获取左表所有记录，即使右表没有对应匹配的记录。
RIGHT JOIN（右连接）： 与 LEFT JOIN 相反，用于获取右表所有记录，即使左表没有对应匹配的记录

#聚合查询
count() :记录查询列有多少行
SUM() :求数值序列的和
AVG() :求平均数
MAX() :求最大值
MIN() :求最小值
```

##### 	<font color="red">1、什么是索引？</font>

​		本质是**帮助MySQL高效获取数据**的**数据结构**，**MySql**中主要应用的索引数据结构为**B+Tree**。

##### 	<font color="red">2、Mysql的数据结构是什么（mysql索引的数据结构）？为什么用这种结构？（如何提高磁盘IO效率）</font>

​		Mysql的数据结构是B+tree，由于数据存储于物理磁盘，所以要尽量减少从磁盘IO数据的次数，有效手段有：

​	    1、磁盘局部预读原理，预读的大小通常为Page的倍数；

​		2、选取合适的数据结构存储数据，从磁盘IO次数越小越好，如BTree，渐进复杂度为O(h)=O(logdN)O(h)=O(logdN)，一般实际应用中，出度d 是非常大的数字，通常超过100，因此树的高度h非常小（通常不超过3层可容纳百万级数据）。所以，B+tree作为mysql数据库的数据结构搜索效率是很高的

##### 	<font color="red">3、Mysql的数据IO查找流程是什么样的？</font>

​		a、**对于聚集索引（主键索引）**来说，也就是通过主键查询，**一次查询**就能查询到**具体的行数据信息**；

​		b、**对于非聚集索引来说（唯一索引、普通索引、全文索引）**如果**需要查询的数据列在索引中**，如A+B联合索引，根据A去查询B，则**通过一次查询**就能直接拿到索引上的数据，也就是**覆盖索引**现象； 如果**需要查询的数据不在索引中**，则需要先**去普通索引树中进行第一次查找**得到行数据的**主键值**，然后**通过主键值去主键索引树**中第二次搜索**得到真实**数据**，这种需要二次查询的现象叫做**回表查询。

​			 详细解释：从普通索引无法直接定位行记录，那**普通索引的查询过程是怎么样的呢？**通常情况下，需要扫码两遍索引树。

##### 	<font color="red">4、B+tree和Btree由什么组成？他们的异同？</font>

​		a、B+tree是B-tree的变体；

​		b、在B-tree的基础上增加了叶子结点间的顺序访问指针，B+Tree提高了顺序访问的性能；

​		c、B-tree每个结点的指针上限为2d+1，B+tree每个结点的指针上限为2d；

​		d、B+tree非叶子结点只存储索引值，叶子结点存储真实数据，B-tree所有结点上都存储数据；

##### 	<font color="red">5、Mysql两种存储引擎（InnoDB和Mysiam）的区别？这两种引擎B+tree的叶子结点和非叶子结点分别存储的什么？</font>

​		**MySIAM**：的索引和数据分两个文件进行存储：MYI文件存储索引(B+树)、MYD文件存储数据，**非叶子节点存储**的是**索引列的值**，**叶子结点存储**的为**真实数据所在的地址**。不支持事务，但每次查询都是原子的，支持表级锁

​		**InnoDB**：的索引和数据存储在一个文件中：ibd文件（B+树）

​			对于非主键索引（非聚集索引）：**非叶子结点**存储的是**索引列的值**，**叶子结点**存储的为**主键ID值**

​			对于主键索引（聚集索引）：**非叶子结点**存储的是**ID值**，**叶子结点**存储的为**完整的数据**

##### 	<font color="red">6、Mysql索引有哪些类型？什么场景使用哪种索引？</font>

​		a. **普通索引：**最基本的索引，它没有任何限制。

​		b. **唯一索引：**与普通索引类似，不同的就是索引列的值必须唯一，但允许有 空值。如果是组合索引，则列值的组合必须唯一。 

​		c. **主键索引：**它是一种特殊的唯一索引，用于唯一标识数据表中的某一条记 录，不允许有空值，一般用 primary key 来约束。**（主键索引通常在建表的时候就指定）**

​		d. **联合索引**（又叫复合索引）：多个字段上建立的索引，能够加速复合查询 条件的检索。 

​		e. **全文索引：**老版本 MySQL 自带的全文索引只能用于数据库引擎为 MyISAM 的数据表，新版本 M+ySQL 5.6 的 InnoDB 支持全文索引。默认 MySQL 不支持中文全文检索，可以通过扩展 MySQL，添加中文全文检索或为中文内容表提供 一个对应的英文索引表的方式来支持中文

##### 	<font color="red">7、如何进行Mysql优化？（sql优化层面和服务器优化层面）</font>

​		**SQL语句层面**

​			a、尽量避免使用select *；

​			b、规范sql语句大小写，sql是有缓存的，避免每次都需要解析；

​			c、合理使用exsits和in，要更高效；exists后面用大表，in后面用小表，也是小表驱动大表的思想，减少表连接的次数提高查询效率

​			d、mysql sql解析执行过程从右至左，基于这个规则，from后面能过滤掉更多数据的基础表放后面，where后面能过滤掉更多数据的查询条件放后面；

​			e、查询条件中用相同类型去查询，比如避免数值列用字符串查询条件（避免隐私转换）；

​			f、合理使用索引

​		**服务器架构两方面进行优化:**

​			*在数据达到一定量级以后，需要对数据库从主从、分库分表数据分片方面进行优化：*

​				 **读写分离**：主节点写，从节点读

​				 **分库**：根据业务或者其他维度把数据存放到不同数据库

​				 **分表**：

​						1、水平分表：字段都一样，分多张表存放不同时间范围或不同维度的数据，如实时数据表、历史数据表。

​						2、垂直分表：将不同字段放在多张表，使用外键关联。

​				常用**分库分表中间件**：阿里的Cobar及开源社区基于Cobar维护的Mycat等。

##### 	<font color="red">8、Sql调优你会从何入手（措施）？</font>

​		1）、尽量避免使用select *；因为需要解析

​		2）、规范sql语句大小写，sql是有缓存的，避免每次都需要解析；

​		3）、合理使用exsits和in，要更高效；exsits后面用大表，in后面用小表

​		4）、mysql sql解析执行过程从右至左，基于这个规则，from后面能过滤掉更多数据的基础表放后面，where后面能过滤掉更多数据的查询条件放后面；

​		5）、查询条件中用相同类型去查询，比如避免数值列用字符串查询条件；

​		6）、合理使用索引

​		7）、还需要分业务场景，具体的是主键查询慢（主键一定要单调递增）还是条件查询慢（覆盖索引），还是分组聚合慢还是深度分页慢（游标思想），到底是怎么影响业务的，

##### 	<font color="red">9、Mysql中如何合理使用索引？有哪些会使索引失效的情况？</font>

​		a、为合适的列添加索引(主键、唯一索引、组合索引)；

​		b、尽量建立联合索引，也省空间成本；

​		c、尽量使用覆盖索引；

​		d、避免以下会使索引失效的操作	

​			1）、索引列有null值不走索引

​			2）、使用is null或is not null不走索引

​			3）、各种负向查询not ，not in， not like ，<> ,!= ,!> ,!<  不会使用索引

​			4）、like将%放左边不走索引

​        	5）、查询条件的数据类型做了隐式转换  varchar类型使用int去查不走索引，int类型使用char去查走索引

​        	6）、使用in或union代替or，or两侧有非索引列就不会走索引

​			7）、尽量保持索引列干净，不在索引列上使用函数转换、运算

​        	8）、联合索引要遵循最左匹配原则.如建立联合索引（A,B,C）,查询顺序如下：ABC会走索引，AB会走索引，A也会走索引，但是不能断开，如AC|CA|BC|CB|B|C都不会走索引

​			9）、使用比较运算或between会使联合索引从使用比较运算的下一个索引处断开

##### 	<font color="red">10、Mysql如何排查慢查询（哪个关键字）？分别会列出来哪些信息项？</font>

​		可以使用explain命令进行sql慢查询排查，分别列出一下信息：

​		1. **id** //select查询的序列号，包含一组数字，表示查询中执行select子句或操作表的顺序，id相同，执行顺序从上至下 //id值越大，优先级越高，越先执行

​	     2. **select_type** //查询类型 SIMPLE、PRIMARY、SUBQUERY、DERIVED、UNION、UNION RESULT

​	     3. table   //正在访问哪个表

​	     4. partitions //匹配的分区

​	     5. **type** //访问的类型  效率从快到慢：NULL>system>const>eq_ref>ref>ref_or_null>index_merge>range>index>ALL

​	     6. possible_keys //显示可能应用在这张表中的索引，一个或多个，但不一定实际使用到

​	      7. **key**    //实际使用到的索引，如果为NULL，则没有使用索引

​	      8. key_len //表示索引中使用的字节数，可通过该列计算查询中使用的索引的长度

​	       9. ref   //显示索引的哪一列被使用了，如果可能的话，是一个常数，哪些列或常量被用于查找索引列上的值

​	      10**. rows** //根据表统计信息及索引选用情况，大致估算出找到所需的记录所需读取的行数，这个数量越小越好

​	       11. filtered //查询的表行占表的百分比

​	       12. Extra //包含不适合在其它列中显示但十分重要的额外信息

##### 	<font color="red">11、事务的特性是什么？Mysql事务隔离级别有哪几种？分别会产生什么问题？Mysql默认隔离级别是什么？Oracle呢？</font>

​		事务的特性是ACID:

​		**Atomicity(原子性)**：事务中所有操作要么全部提交成功，要么全部失败回滚，不能出现一部分失败，一部分成功的现象，由undo log日志保证，他记录了需要回滚得日志信息，事务回滚时撤销已经执行成功的SQL；

​		**Consistency(一致性)**：指在事务的执行前后保持数据库的一致性,由其他三大特性去保证，代码也要保证业务上的一致性；

​		**Isolation(隔离性)**：一个事务所做的修改在最终提交之前，对其他事务是不可见的，由MVCC来保证；

​		**Durability(永久性)**：一旦事务提交，它所做的修改将会永久保存到数据库中，及时系统发生崩溃，事务执行结果也不会丢失，由内存+redo log来保证，mysql修改数据同时在内存和redo log记录这次操作；

​		**事务的隔离级别有一下4种**

|         事务隔离级别         | 脏读 | 不可重复读 | 幻读 |
| :--------------------------: | ---- | ---------- | ---- |
| 读未提交（read-uncommitted） | 是   | 是         | 是   |
| 不可重复读（read-committed） | 否   | 是         | 是   |
| 可重复读（repeatable-read）  | 否   | 否         | 是   |
|    串行化（serializable）    | 否   | 否         | 否   |

​		**脏读**：**一个事物**读到了**另一个事务尚未提交**的数据，不符合事务的隔离性。

​		**不可重复读**：**同一个事务中**针**对同一行记录两次**读出来的**结果不一样**，原因就是第二次读到了其他事务**修改提交**的数据。

​		**幻读**：**同一个事务中**针对**同一范围内的数据**两次读出来的**结果不一样**，原因就是第二次读到了其他事务**新增提交**的数据。

​		**mysql默认隔离级别**：repeatable-read，但是一般会设置为read-committed，因为在实际业务中常常是：一个事务中需要读到别的事务提交修改的数据。

​		**oraclel默认隔离级别**：read-committed

##### 	<font color="red">12、Mysql的读锁、写锁、行锁、表锁，悲观锁、乐观锁？</font>

​		**读锁：**也叫共享锁、S锁，若事务T对数据对象A加上S锁，则事务T可以读A但不能修改A，其他事务只能再对A加S锁，而不能加X锁，直到T释放A上的S 锁。这保证了其他事务可以读A，但在T释放A上的S锁之前不能对A做任何修改。

​		**写锁：**又称排他锁、X锁。若事务T对数据对象A加上X锁，事务T可以读A也可以修改A，其他事务不能再对A加任何锁，直到T释放A上的锁。这保证了其他事务在T释放A上的锁之前不能再读取和修改A。

​		**行锁：**操作对象是数据表中的一行。是MVCC技术用的比较多的，但在MYISAM用不了，行级锁用mysql的储存引擎实现而不是mysql服务器。但行级锁对系统开销较大，处理高并发较好。

​		**表锁：**操作对象是数据表。Mysql大多数锁策略都支持(常见mysql innodb)，是系统开销最低但并发性最低的一个锁策略。事务t对整个表加读锁，则其他事务可读不可写，若加写锁，则其他事务增删改都不行。

​		**悲观锁：** **悲观的认为**本次事务**一定会有别的事务干扰**，操作数据前**必须先加锁**常见实现方式为 for update加**行锁**： select ... from table where id = #{id} for update，这里注意，由于**mysql锁是建立在索引上面**的，所以查询条件必须用**主键索引**，否则会造成**数据全表扫描**。

​		**乐观锁：** **乐观的认为**本次事务操作数据**不会有别的事务干扰**，操作数据前**不进行加锁**，只是**预先记录版本号**，真正修改数据时**再进行比对**，如果版本号没变则修改数据，版本号变了则表面别的事务在本次事务过程中修改了数据，本次事务不修改数据。

##### 	<font color="red">13、Mysql的vachar和char的区别？</font>

​		**char列长度固定**，为创建表时声明的长度，长度值范围是1到255，当char值未填满指定长度时，其他空间会用**空格**进行填充，检索CHAR值时需删除尾随空格。

​		**vachar长度为可变的**，实际使用多少空间就占多少空间。

##### 	<font color="red">14、什么是内连接(inner join)、外连接（left join）？笛卡尔积</font>

​		**内连接：**是一种最常用的连接类型。内连接查询实际上是一种任意条件的查询。使用内连接时，如果两个表的相关字段满足连接条件，就从这两个表中提取数据并组合成新的记录，也就是在内连接查询中，只有满足条件的元组才能出现在结果关系中。

​		**外连接：**分为全外连接、左外连接、右外连接，就是把两张表的数据显示出来；

​	<font color="red">15、平时Mysql的sql练习要练到位！！</font>

##### 	<font color="red">17、mybatis #{}和${}的区别？</font>

​		（1）#{}：参数占位符，即预编译,很大程度上能防止sql 注入,编译好SQL后语句再去取值

​		（2）${} ：字符串替换符，即SQL拼接,取值以后再去编译SQL语句

##### 	<font color="red">18、Mysql存储过程、存储函数、触发器、视图（View）分别用来干嘛的？创建语法是什么？</font>

​	存储过程

```

```



##### 	<font color="red">19、union和unionAll有什么区别？</font>

​		**union:** 对两个结果集进行并集操作, 不包括重复行,相当于distinct, 同时进行默认规则的排序;会对获取的结果进行排序操作

​		**union all:** 对两个结果集进行并集操作, 包括重复行, 即所有的结果全部显示, 不管是不是重复;不会对获取的结果进行排序操作

​		union all只是合并查询结果，并不会进行去重和排序操作，在没有去重的前提下，使用union all的执行效率要比union高

##### 	<font color="red">20、创建表、删除表、更新表字段语句？</font>

​		**创建表：**create [kriˈeɪt]   table 表名（）

​		**删除表：**drop table 表名；

​		**更新表：**

​			a.添加列：**alter table** 表名 **add** 列名 指定列表数据类型

​			b.删除列：**alter table** 表名 **drop column** 列名 (禁用)

​			c.改变数据类型：**alter table** 表名 **alter column** 列名 修改的新数据类型

​			d.改变表名：**alter table** 表名**change** 旧列名 新列名

##### 	<font color="red">21、mysql左外连接语句的写法？</font>		

```
select 字段名 from 表名 left join 表名 on 条件
```

##### 	<font color="red">22、听过InnoDB的Mvcc技术吗？说下是什么？</font>

​		**MVCC (Multiversion Concurrency Control)**，即多版本并发控制技术,它使得大部分支持行锁的事务引擎，不再单纯的使用行锁来进行数据库的并发控制，取而代之的是把数据库的行锁与行的多个版本结合起来，只需要很小的开销,就可以实现非锁定读，从而大大提高数据库系统的并发性能，我觉得可以先从数据库的三种并发场景说起

**第一种：读读**

​	就是线程 A 与线程 B 同时在进行读操作，这种情况下不会出现任何并发问题

**第二种：读写**

就是线程 A 与线程 B 在同一时刻分别进行读和写操作。 这种情况下，可能会对数据库中的数据造成以下问题： 

​		 事物隔离性问题， 

​		出现脏读，幻读，不可重复读的问题

**第三种：写写**

就是线程 A 与线程 B 同时进行写操作 

这种情况下可能会存在数据更新丢失的问题。 

而 MVCC 就是为了解决事务操作中并发安全性问题的无锁并发控制技术全称为 Multi-Version Concurrency Control ，也就是多版本并发控制。它是通过数据库记录中的隐式字段，undo日志 ，Read View 来实现的。

MVCC 主要解决了三个问题 

​		第一个是：通过 MVCC 可以解决读写并发阻塞问题从而提升数据并发处理能力 

​		第二个是：MVCC 采用了乐观锁的方式实现，降低了死锁的概率 

​		第三个是：解决了一致性读的问题也就是事务启动时根据某个条件读取到的数据，直到事务结束时，再次执行相同条件，还是读到同一份数据，不会发生变化。 而我们在使用 MVCC 时一般会根据业务场景来选择组合搭配乐观锁或悲观锁。 这两个组合中，MVCC 用来解决读写冲突，乐观锁或者悲观锁解决写写冲突从而最大 程度的提高数据库并发性能。 以上就是我的对 MVCC 的理解

##### <font color="red">23、count(1)、count(*)、count(列名)的区别？</font>	

​	**执行效果上 ：** 

​		 count(*)包括了所有的列，相当于行数，在统计结果的时候， 不会忽略列值为NULL 
 		count(1)包括了忽略所有列，用1代表代码行，在统计结果的时候， 不会忽略列值为NULL 
 		count(列名)只包括列名那一列，在统计结果的时候，会忽略列值为空（这里的空不是只空字符串或者0，而是表示null）的计数， 即某个字段值为NULL时，不统计。

​	**执行效率上：** 
​		列名为主键，count(列名)会比count(1)快 
​		列名不为主键，count(1)会比count(列名)快 
​		如果表多个列并且没有主键，则 count（1） 的执行效率优于 count（*） 
​		如果有主键，则 select count（主键）的执行效率是最优的 
​		如果表只有一个字段，则 select count（*）最优。

##### <font color="red">24、Mysql读写分离数据同步原理</font>

​	1、用户授权

​	2、启用binlog日志

​	Log Dump线程：

​	IO线程： 把master 库的 binlog日志内容 记录到本机的relay-binlog（中继）日志里。

​	SQL线程：（slave）执行本机relay-binlog日志里的sql命令 把数据写进本机的库。

##### 	<font color="red">25、Mybatis底层的原理？一级缓存和二级缓存是什么？</font>

​		mybatis的的一级缓存是SqlSession级别的缓存，一级缓存缓存的是对象，当SqlSession提交、关闭以及其他的更新数据库的操作发生后，一级缓存就会清空。

​		二级缓存是SqlSessionFactory级别的缓存，同一个SqlSessionFactory产生的SqlSession都共享一个二级缓存，二级缓存中存储的是数据，当命中二级缓存时，通过存储的数据构造对象返回。查询数据的时候，查询的流程是二级缓存>一级缓存>数据库。

##### <font color="red">26、SQL解析过程</font>

(1)FROM < table source >数据源解析

(2)WHERE < condition >

(3)GROUP BY < group by list >

(4)HAVING < having condition >

(5)SELECT 

(6)DISTINCT < select list >

(7) ORDER BY < order by list >

# 五、多线程

​	线程（Thread）是操作系统能够进行运算调度的基本单位。它包含在进程中，是进程中的实际运行单位。

##### <font color="red">0、什么情况下使用单线程什么情况下使用多线程？</font>

1、一个请求过来处理时间需要很久使用多线程

2、很多请求过来但处理起来很快，使用单线程

##### 	<font color="red">1、创建线程的方式有哪些？相比继承Thread类，实现Runable接口的好处是什么？</font>

​		1、继承 Thread 类并重写 run 方法创建线程，实现简单但不可以继承其他类 

​		2、实现 Runnable 接口并重写 run 方法。避免了单继承局限性，编程更加灵活，实 现解耦。无返回值，只能抛出运行时异常，不能捕获异常 

​		3、实现 Callable 接口并重写 call 方法，创建线程。可以获取线程执行结果的返回 值，并且可以抛出异常，可以捕获异常信息。

​		4、使用线程池创建（使用 java.util.concurrent.Executor 接口）

​		Java是单继承，多实现的，避免了单继承局限性，编程更加灵活，实 现解耦。

##### <font color="red">1、停止线程的方法有哪些？</font>

​		1、stop方法（不同）

​		2、使用共享变量(少用)

​		3、interrupt方式

##### 	<font color="red">2、线程的状态有哪些？</font>

​		1、第一是 **new->新建状态**。在生成线程对象，并没有调用该对象的 start 方法，这是线程处于 创建状态。 

​		2、第二是 **Runnable->就绪状态**。当调用了线程对象的 start 方法之后，该线程就进入了就绪 状态，但是此时线程调度程序还没有把该线程设置为当前线程，此时处于就绪状态。 

​		3、 第三是 **Running->运行状态**。线程调度程序将处于就绪状态的线程设置为当前线程，此时线 程就进入了运行状态，开始运行 run 函数当中的代码。

​		4、第四是**阻塞状态**。阻塞状态是线程因为某种原因放弃 CPU 使用权，暂时停止运行。直到线程 进入就绪状态，才有机会转到运行状态。阻塞的情况分三种：

​			 a、等待 – 通过调用线程的 wait() 方法，让线程等待某工作的完成。 

​			b、超时等待 – 通过调用线程的 sleep() 或 join()或发出了 I/O 请求时，线程会进入到阻塞状态。 当 sleep()状态超时、join()等待线程终止或者超时、或者 I/O 处理完毕时，线程重新转入就绪状 态。 

​			c、同步阻塞 – 线程在获取 synchronized 同步锁失败(因为锁被其它线程所占用)，它会进入同 步阻塞状态。 

5、 第五是 **dead->死亡状态**: 线程执行完了或者因异常退出了 run()方法，该线程结束生命周期.

##### 	<font color="red">3、run()和start()方法有哪些区别？</font>

​		线程对象调用 run 方法不开启线程。仅是对象调用方法。 线程对象调用 start 开启线程，并让 jvm 调用 run 方法在开启的线程中执行 调用 start 方法可以启动线程，并且使得线程进入就绪状态，而 run 方法只是 thread 的一 个普通方法，还是在主线程中执行。

##### 	<font color="red">4、实现线程间通讯的方法有哪些？</font>

​		join() 方法：`join()` 方法是 Thread 类的一个实例方法。它的作用是**让当前线程陷入“等待”状态，等 join 的这个线程执行完成后，再继续执行当前线程**。

​		sleep() 方法：`sleep()` 方法是 Thread 类的一个静态方法。它的作用是**让当前线程睡眠一段时间**

​		InheritableThreadLocal：**InheritableThreadLocal** 类与 ThreadLocal 类稍有不同，Inheritable 是继承的意思。它不仅仅是当前线程可以存取副本值，而且它的子线程也可以存取这个副本值。

##### 	<font color="red">5、wait、notify、notifyAll分别的作用是什么？可以用在同步代码块之外吗？为什么？</font>

​		**wait(线程等待)**调用该方法的线程进入 WAITING 状态，只有等待另外线程的通知或被中 断才会返回，需要注意的是调用 wait()方法后，会释放对象的锁。因此，wait 方 法一般用在同步方法或同步代码块中

​		**线程唤醒（notify）**Object 类中的 notify() 方法，唤醒在此对象监视器上等待的单个线程，如 果所有线程都在此对象上等待，则会选择唤醒其中一个线程，选择是任意的，并 在对实现做出决定时发生，线程通过调用其中一个 wait() 方法，在对象的监视 器上等待，直到当前的线程放弃此对象上的锁定，才能继续执行被唤醒的线程， 被唤醒的线程将以常规方式与在该对象上主动同步的其他所有线程进行竞争。类 似的方法还有 notifyAll() ，唤醒再次监视器上等待的所有线程。

​			1）、从**运行层面**来说，如果写在别的位置会报非法监视器异常，这里的**监视器**就是**锁对象**；

​			2）、从**原理层面**来说

​				这三个方法是用于**线程间通讯的**，而控制线程通讯的**主体是锁对象**，使用这三个方法控制线程通讯的时候必须**先通过Synchronized获取并指定锁对象**。更具体点，如wait()方法会释放锁，释放锁之前必须先通过Synchronized同步代码块获取锁。

​				**理解**：**锁对象**维护着一个**等待队列list**，通过锁对象**调用wait()**方法则**会让线程进入这个等待队列list**，调用**notifyAll方法**则会**从队列list中取出这个线程继续执行**。

##### 	<font color="red">6、Sleep和Wait的区别？</font>

|              | wait()           | sleep()          |
| ------------ | ---------------- | ---------------- |
| 来自类       | Object类         | Thread类         |
| 是否释放锁   | 等待时会释放锁   | 等待时不会释放锁 |
| 使用范围     | 必须同步代码块中 | 任何地方         |
| 释放捕获异常 | 不需要捕获异常   | 需要捕获异常     |

##### 	<font color="red">7、什么是线程安全问题？什么情况下会产生？如何解决？</font>

​		**线程安全问题**就是 多线程环境中 , 且存在数据共享 , 一个线程访问的共享 数据被其他线程修改了, 那么就发生了线程安全问题 , 整个访问过程中 , 无一共享的数据被其他线程修改了 就是线程安全的程序中如果使用成员变量, 且对成员变量进行数据修改 , 就存在数据共享问题, 也就是线程安全问题。

​		当**多个线程同时共享一个[全局变量](https://so.csdn.net/so/search?q=全局变量&spm=1001.2101.3001.7020),**或者静态变量的情况下, 进行写的操作时, 可能会发生数据的冲突问题 ,也就是线程安全问题, 但是做读的操作不会引发线程安全问题

​		**解决：**

​			1、使用同步机制, 使得在同一时间只能有一个线程修改共享数据

​			2、消除共享数据, 即多个线程数据不共享或者共享的数据不被做修改 如果使用成员变量, 对成员变量不进行修改（使用final修饰）



##### <font color="red">8、Java中锁的分类？</font>

a、线程要不要锁住同步资源（悲观锁、乐观锁）

b、多线程能否共享一把锁（共享锁、排他锁）

c、多线程竞争时是否需要排队（公平锁、非公平锁）

d、同一个线程是否可以重复获取同一把锁（可重入锁、不可重入锁）

e、是否可以中断（可中断锁、非可中断锁）

f、等锁的过程（自旋锁、非自旋锁）

##### 	<font color="red">8、什么是死锁？如何防止产生死锁？</font>

​		多个进程或线程互相等待对方的资源，在得到新的资源之前不会释放自己的资源，这样就形成了循环等待，这种现象被称为**死锁**。

​		<font color="#ff00ff">产生死锁的必要条件</font>

​		**环路等待：**死锁发生时，系统中必定有两个或两个以上的进程或线程组成一条等待环路。

​		**占有且请求：**已经得到资源的进程或线程，继续请求新的资源，并持续占有旧的资源。

​		**资源互斥：**资源只有两种状态，只有可用和不可用两状态，不能同时使用，同一时刻只能被一个进程或线程使用。

​		**资源不可剥夺：**资源已经分配进程或线程后，不能被其它进程或线程强制性获取，除非资源的占有者主动释放。

​		注意：死锁一旦产生基本无解，现在的操作系统无法解决死锁，因此只能防止死锁产生。

​		<font color="#ff00ff">防止产生死锁的方法</font>

​		**破坏占用且请求条件：**采用预先静态分配的方法，进程或线程在运行前一次申请所有资源，在资源没有满足前不投入运行。

​		**缺点：**系统资源会被严重浪费，因为有些资源可能开始时使用，而有些资源结束时才使用。

​		**破坏不可剥夺条件：**当一个进程或线程已经占有一个不可剥夺的资源时，请求新资源时无法满足，则释放已经占有的资源，一段时间后再重新申请。
​		**缺点：**该策略实现起来比较复杂，释放已经获取资源可能会导致前一阶段的工作失效，反复的申请释放资源会增加系统开销，占用CPU和寄存器、内存等资源。

​		**破坏循环等待条件：**给每个资源进行编号，进程或线程按照顺序请求资源，只有拿到前一外资源，才能继续请求下一个资源。
​		**缺点：**资源的编号必须相对稳定，资源添加或销毁时会受到影响。

​		**算法：**银行家算法

##### 	<font color="red">9、Synchronized关键字的底层原理是什么?</font>

​		synchronized 可以保证方法或者代码块在运行时，同一时刻只有一个方法可以进 入到临界区，同时它还可以保证共享变量的内存可见性。

​		首先，java对象分为【**对象头**】、【**对象实例数据**】等几部分数据，这里由对象头中的**Mard Word**部分记录对象的锁信息。

​		 其次，通过编译后的字节码文件可看出，上锁和解锁指令，同步代码块是使用monitorenter和monitorexit指令实现的，同步方法（字节码中看不出来需要看JVM底层实现）依靠的是方法修饰符上的ACC_SYNCHRONIZED实现。

##### 	<font color="red">10、Synchronized可以用在哪些地方？分别的锁对象是什么？</font>

​			1）、同步代码块：锁对象为括号中的对象

​			2）、同步方法：锁对象为当前对象 this

​			3）、静态同步方法：锁对象为class字节码文件对象

##### 	<font color="red">11、Synchronized和JUC下Lock锁的异同？(java.util.concurrent 并发编程包是专门为 Java 并发编程设计的)</font>

​		1）、**Lock**是JUC包下提供的**封装好的锁**，是**类**的概念，而**synchronized**是一个**虚拟机层面的关键字**。

​		2）、**Lock显示的加锁和解锁**，且解锁要在finally代码块中，否则可能会死锁，而**synchronized**为**隐式的上锁和解锁**。

​		3）、**Lock**锁提供了**尝试获取锁**和**设置获取锁时间**的**机制**，可返回**取锁状态**，当获取不到锁的时候也**可以选择放弃取锁**，而**synchronized无法判断返回取锁状态**，取锁不成功**只能阻塞**，**没有Lock灵活**。

​		4）、**Lock**锁**阻塞可被打断**，而**synchronized**阻塞**不可被打断**。

​		5）、**Lock**可实现**可重入、可公平锁**，而**synchronized**是**可重入、非公平锁**。

​		6）、**Lock**可以很灵活的根据线程角色类型去**创建Condition监视器对象**，调用**await()、signal()、signalAll()**进行线程通讯调度，而**synchronized**使用**Object对象本身**作为**监视器对象**去调用**wait() 、notify()、notifyAll()**进行线程通讯调度。

​		7）、Lock提供了更丰富的锁分类，如读锁、写锁，可以更细粒度的关注线程安全问题。

##### 	<font color="red">13、Synchronized在JDK1.6做了什么优化？</font>

 		自适应的CAS自旋、锁消除、锁粗化、偏向锁、轻量级锁

##### 	<font color="red">12、Synchronized是公平锁还是非公平锁？获取不到锁时会阻塞吗？</font>

​		非公平的，新来的线程有可能立即获取监视器（锁），而在等待区等了很久的线程可能还会再次等待，这样有利于提高性能，但也会导致饥饿现象。

##### 	<font color="red">13、同步代码块中执行完wait/notify/notifyAll后会立马释放锁吗？</font>

​	不会，需要同步代码块执行完才会释放锁

##### 	<font color="red">14、Lock锁有哪些实现？分别的特点是什么？</font>

Lock本质上是一个接口，它定义了释放锁和获得锁的抽象方法，定义成接口就意味着它定义了锁的一个标准规范，也同时意味着锁的不同实现。实现Lock接口的类有很多，以下为几个常见的锁实现

**ReentrantLock：表示重入锁**，它是唯一一个实现了Lock接口的类。重入锁指的是线程在获得锁之后，再次获取该锁不需要阻塞，而是直接关联一次计数器增加重入次数；

**ReentrantReadWriteLock：重入读写锁**，它实现了ReadWriteLock接口，在这个类中维护了两个锁，一个是ReadLock，一个是WriteLock，他们都分别实现了Lock接口。读写锁是一种适合读多写少的场景下解决线程安全问题的工具，基本原则是：&nbsp;读和读不互斥、读和写互斥、写和写互斥。也就是说涉及到影响数据变化的操作都会存在互斥。

**StampedLock：&nbsp;stampedLock是JDK8引入的新的锁机制**，可以简单认为是读写锁的一个改进版本，读写锁虽然通过分离读和写的功能使得读和读之间可以完全并发，但是读和写是有冲突的，如果大量的读线程存在，可能会引起写线程的饥饿。stampedLock是一种乐观的读策略，使得乐观锁完全不会阻塞写线程

##### 	<font color="red">15、JUC下Lock的监视器对象是哪个类？与Synchronized的监视器有什么异同？</font>

​		1.synchronized是一个关键字而lock是一个接口（lock、lockInterruptibly、tryLock、unlock、newCondition）。

​		2.synchronized是隐式的加锁，lock是显示的加锁。

​		3.synchronized可以作用在方法和代码块上，而lock只能作用在代码块上。
synchronized作用在静态方法上锁的是当前类的class，作用在普通方法上锁的是当前类的对象。
在javap反编译成字节码后，synchronized关键字需要有一个代码块进入的点monitorenter，代码块退出和代码块异常的出口点monitorexit。

​		4.synchronized是阻塞式加锁，而lock中的trylock支持非阻塞式加锁。

​		5.synchronized没有超时机制，而lock中的trylcok可以支持超时机制。

​		6.synchronized不可中断，而lock中的lockInterruptibly可中断的获取锁。（ReentrantLock.lockInterruptibly允许在等待时由其它线程调用等待线程的Thread.interrupt方法来中断等待线程的等待而直接返回，这时不用获取锁，而会抛出一个InterruptedException。 ReentrantLock.lock方法不允许Thread.interrupt中断,即使检测到Thread.isInterrupted,一样会继续尝试获取锁，失败则继续休眠。只是在最后获取锁成功后再把当前线程置为interrupted状态,然后再中断线程。）

​		7.synchronized采用的是monitor对象监视器，lock的底层原理是AQS

​		8.synchronized只有一个同步队列和一个等待队列，而lock有一个同步队列，可以有多个等待队列。
​			同步队列：排队取锁的线程所在的队列。
​			等待队列：调用 wait 方法后，线程会从同步队列转移到等待队列。

​		9.synchronized是非公平锁，而lock可以是公平锁也可以是非公平锁。

​		10.synchronized用object的notify方法进行唤醒，而lock用condition进行唤醒。

​		11.lock有ReadWriteLock支持并发读

##### 	<font color="red">16、什么是线程可重入？Synchronized具备吗？Lock呢？</font>

​	  在一个线程中某个方法获取锁后，进入该线程的其他方法时不需要重新取锁叫做线程可重入，synchronized具备线程可重入特性。

##### 	<font color="red">17、什么是AQS？</font>

​		**`java.util.concurrent.locks.AbstractQueuedSynchronizer`** 抽象类，简称 **AQS** ，是一个用于构建锁和同步容器的**队列同步器**，它是整个JUC包下Lock体系的核心，如ReentrantLock、ReentrantReadWriteLock、CountDownLatch、Semaphore都是基于它来实现的，它 解决了在实现同步容器时设计的大量细节问题，它的核心构成部分为：使用一个 **先进先出的FIFO 的队列**存储排队**等待锁的线程**，使用**一个用volatile修饰的int类型的state同步状态**来记录**当前是否有线程持有锁**，0表示没有线程获得锁，1表示有，上锁state就加1，释放锁就对应减1，有重入锁现象，这个值就大于1，然后需要逐级去释放。

##### 	<font color="red">18、什么是CAS？什么是CAS的ABA问题？如何解决？</font>

​		**`CAS`**其实就是**乐观锁**的一种实现方式，而**悲观锁**比较典型的就是`Java`中的**`synchronized`**。

​					**`CAS`**全称`compare and swap`——**比较并替换**，保证对数据更改的**原子性**，它是**并发条件下修改数据**的**一种机制**，包含**三个操作数**：

​							> 需要修改的数据的内存地址（V）；

​							> 对这个数据的旧预期值（A）；

​							> 需要将它修改为的值（B）；

​				    CAS的操作步骤如下：

> ​							1）、修改前记录数据的内存地址V；
>
> ​							2）、读取数据的当前的值，记录为A；
>
> ​							3）、需要修改值时查看地址V下的值是否仍然为A，若为A，则用B替换它；若地址V下的值不为A，表示在自己修改的过程中，其他的线程对数据进行
>
> ​									了修改，则不更新变量的值，而是重新从步骤2开始执行，这被称为**自旋**；
>
> ​				    CAS 贯穿于整个AQS体系，是AQS实现的基础。
>
> ​				      **（1）优点**
>
>   						   `CAS`是一种乐观锁，其优点就是不需要加锁就能进行原子操作；
>
>  				     **（2）缺点**
>
>  				 	      `CAS`的缺点主有三点：
>
> ​									       `CAS`机制只能用在对某一个变量进行原子操作，无法用来保证多个变量或语句的原子性（`synchronized`可以）；
>
> ​									       假设在修改数据的过程中经常与其他线程修改冲突，将导致需要多次的重新尝试；
>
> ​										   有可能产生ABA问题；
>
>     				  **（3）适用场景** 
>
>  							 由上面分析的优缺点可以看出，`CAS`适用于并发冲突发生频率较低的场合，而对于并发冲突较频繁的场合，`CAS`由于不断重试，反倒会降低效率。
>
> ​      		   	**总结**：`CAS`是一种在并发下实现原子操作的机制，但是只能用来保证一个变量的原子性，适用于并发冲突频率较低的场合。
>
> ​					 **补充**：关于数值类型操作原子性问题：
>
> ​					 `int++` 并不是一个原子操作，所以当一个线程读取它的值并加 1 时，另外一个线程有可能会读到之前的值，这就会引发错误。
>
> ​					 JDK5 后，`java.util.concurrent.atomic` 包提供了 `int` 和 `long` 类型的原子包装类，它们可以自动的保证对于他们的操作是原子的并且不需要使用同步。

##### 	<font color="red">19、你了解JUC下的哪些工具类，分别有什么作用？（CountdownLatch、Cyclicbarrier、Simephore）</font>

​	<font color="#ff00ff">	1）、CountdownLatch </font>

​		具有**计数器**的功能，**构造方法初始化数量**，通常**调用await方法**控制某个线程**等待**，其他线程执行完会countDown一次进行减1，直到countDown为0才会执行阻塞的线程

​		值得注意的是CountDownLatch计数的次数一定要与构造器传入的数字一致，比如构造器传入的是3，则countDown()一定要执行3次，否则线await的进程将一直阻塞。

​		**CountDownLatch通常用来控制某个线程等待，让某组线程执行完才能执行调用await的线程。**

​	<font color="#ff00ff">	2）、Cyclicbarrier </font>

​		类似CountdownLatch，区别是线程在countDown()之后，会继续执行自己的任务，而CyclicBarrier会在**所有线程任务结束之后**，**才会进行后续任务**。两者区别：

| CountDownLatch                                               | Cyclic Barrier                                               |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 减计数方式                                                   | 加计数方式                                                   |
| 计算为0时释放所有等待的线程                                  | 计数达到指定值时释放所有等待的线程                           |
| 计数为0时，无法重置                                          | 计数达到指定值时，计数置为0，重新开始                        |
| 调用countDown()方法计数减1，调用await()方法只进行阻塞，对计数没有任何影响 | 调用await()方法计数加1，若加1或的值不等于构造方法的值，线程阻塞 |
| 不可重复利用                                                 | 可重复利用                                                   |

​		<font color="#ff00ff">3）、Simephore</font>

​		也是一种计数器，用来**保护一个或者多个共享资源的访问**。如果线程要访问一个资源就**必须先获得信号量**。如果信号量内部计数器大于0，信号量减1，

​		然后允许共享这个资源；否则，如果信号量的计数器等于0，信号量将会把线程置入休眠直至计数器大于0，当信号量使用完时，必须释放。

​		**Simephore常用于控制某一共享资源访问的访问线程的最大数量。**

##### 	<font color="red">20、说下volatile关键字，有什么作用？原理是什么？</font>

​				volatile  是java关键字，是一个变量类型修饰符，被voltile修饰的变量具有以下特性：

​		**可见性**：保证了不同线程对这个变量进行操作时的可见性，即**一个线程修改**了某个**变量的值**，这**新值对其他线程来说**是**立即可见**的。

​		实现(缓存共享协议)：

​			对于用volatile形容的变量，线程**写入本地内存中的同时**会将数据**立即刷新到主内存中**。

​			其他线程读取该变量时，发现被volatile修饰，会**将本地变量值置为无效**，然后**从主内存中读取**。

​		**有序性**：禁止进行指令重排序。为提高执行效率，在不影响最终执行结果的前提下，代码在编译成字节码的时候有可能进行**指令重新排序**，这在**单线程情况下是没有问题的**，但是在**多线程的情况下会出现问题**。**volatile修饰的变量**则**可以避免这个问题**。

​		**不保证原子性**：volatile 只能保证对单次读/写的原子性。i++ 这种操作不能保证原子性。关于volatile 原子性可以理解为把对volatile变量的单个读/写，看成是使用同一个锁对这些单个读/写操作做了同步。

##### 	<font color="red">21、说下ThreadLocal，有什么作用？有哪些主要方法，实现原理是什么？为什么会有内存泄漏问题？如何解决？</font>

​		**ThreadLocal**是除了**加锁**这种**同步方式之外**的另一种**可以规避出现多线程安全问题**的思路。

​		ThreadLocal是JDK包提供的，它提供**线程本地变量**，如果创建一个ThreadLocal变量，那么访问这个变量的**每个线程**都会有这个**变量的一个副本**，在实际多线程操作的时候，操作的是**自己本地内存中的变量**，从而**规避了线程安全问题**

​		**主要方法有：get（）、set（）、remove（）**

​		**实现原理：每个线程**都有属于自己的一个**ThreadLocalMap**，可通过Thread获得，这个map存储着**以threadLock对象为key**、**以设置的值为value**的键值对。调用get或者set还有remove方法都是操作这个map可能造成的问题：**内存泄漏**：

​					对于线程池里面不会销毁的线程, 里面总会存在着<ThreadLocal, LocalVariable>的强引用, 因为`final static` 修饰的 `ThreadLocal` 并不会释放,而`ThreadLocalMap` 对于 Key 虽然是弱引用, 但是强引用不会释放, 弱引用当然也会一直有值, 同时创建的`LocalVariable`对象也不会释放, 就造成了内存泄露; 如果`LocalVariable`对象不是一个大对象的话, 其实泄露的并不严重, `泄露的内存 = 核心线程数 * LocalVariable对象的大小`;

​					 **解决**： 为了避免出现内存泄露的情况, **ThreadLocal**提供了一个**清除线程中对象**的方法, 即 **`remove`**, 其实内部实现就是调用 `ThreadLocalMap` 的`remove`方法

##### 	<font color="red">22、说下线程池的几大核心参数？分别有什么作用？有几种默认的线程池？他们的7个核心参数为什么要那么设置？</font>

​	<font color="#ff00ff">线程池七大核心参数</font>

​		**corePoolSize：**核心线程池的大小 

​		**maximumPoolSize：**线程池能创建线程的最大个数 

​		**keepAliveTime：**空闲线程存活时间 

​		**unit：**时间单位，为 keepAliveTime 指定时间单位 

​		**workQueue：**阻塞队列，用于保存任务的阻塞队列 

​		**threadFactory：**创建线程的工程类 

​		**handler：**饱和策略（拒绝策略）

​	<font color="#ff00ff">五种默认线程池</font>

​		1、 **newCachedThreadPool：**创建一个可进行缓存重复利用的线程池 

​		2、**newFixedThreadPool：**创建一个可重用固定线程数的线程池，以共享的无 界队列方式来运行这些线程，线程池中的线程处于一定的量，可以很好的控制线程的并发量 

​		3、**newSingleThreadExecutor ：** 创 建 一 个 使 用 单 个 worker 线 程 的 Executor ，以无界队列方式来运行该线程。线程池中最多执行一个线程，之后提交的线程 将会排在队列中以此执行 

​		4、**newSingleThreadScheduledExecutor：**创建一个单线程执行程序，它可 安排在给定延迟后运行命令或者定期执行 

​		5、**newScheduledThreadPool：**创建一个线程池，它可安排在给定延迟后运行 命令或者定期的执行 

​		6、**newWorkStealingPool：**创建一个带并行级别的线程池，并行级别决定了 同一时刻最多有多少个线程在执行，如不传并行级别参数，将默认为当前系统的 CPU 个数

​	<font color="#ff00ff">四大拒绝策略</font>

​		**ThreadPoolExecutor.AbortPolicy（系统默认）**： 丢弃任务并抛出 RejectedExecutionException 异常，让你感知到任务被拒绝了，我们可以根据业务逻辑选 择重试或者放弃提交等策略 

​		**ThreadPoolExecutor.DiscardPolicy：**也是丢弃任务，但是不抛出异常，相对而 言存在一定的风险，因为我们提交的时候根本不知道这个任务会被丢弃，可能造成数据丢失。 

​		**ThreadPoolExecutor.DiscardOldestPolicy：** 丢弃队列最前面的任务，然后重新尝试执 行任务（重复此过程），通常是存活时间最长的任务，它也存在一定的数据丢失风险 

​		**ThreadPoolExecutor.CallerRunsPolicy：**既不抛弃任务也不抛出异常，而是将某些任务 回退到调用者，让调用者去执行它

##### <font color="red">23、为什么不建议使用Executors来创建线程池？</font>

##### <font color="red">23、线程池有哪几种状态？</font>

##### 	<font color="red">23、单例模式写法有哪几种？（懒汉和饿汉式）那么懒汉式中保证线程安全的写法是什么？为什么要用双重检查模式？</font>

​		**单例模式：**某个类的实例在 多线程环境下只会被创建一次出来。 

​		单例模式有**饿汉式单例模式**、**懒汉式单例模式**和**双检锁单例模式**三种。

​		**饿汉式：**线程安全，一开始就初始化

```java
public class Singleton{
    private static Singleton instance = new Singleton();
    private Singleton(){}
    public static Singleton getInstance(){
        return instance;
    }
}
```

​		**懒汉式：**非线程安全，延迟初始化

```java
public class Singleton{
    private static Singleton instance = new Singleton();
    private Singleton(){}
    
    public static Singleton getInstance(){
        if(instance == null){
            instance = new Singleton();
        }
        return instance;
    }
}
```

​		**双检锁：**线程安全，延迟初始化

```java
public class Singleton{
    private static Singleton instance = new Singleton();
    private Singleton(){}
    
    public static Singleton getInstance(){
        if(instance == null){  //第一次循环是效率
            synchronized(Singleton.class){
                if(instance == null){   //第二次是保证单例
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}
```



# 六、Redis & 多级缓存

##### 	<font color="red">1、Redis是一个什么样的数据库？读写速度怎么样？</font>

​		Redis 是 C 语言开发的一个开源的（遵从 BSD 协议）高性能非关系型（NoSQL） 的（key-value）键值对数据库。读写速度快的原因：

​			a、redis完全基于内存

​			b、数据结构简单

​			c、采用单线程，避免了加锁、释放锁、死锁、线程间切换等消耗

​			d、使用多路I/O复用模型，非阻塞IO

##### 	<font color="red">2、Redis有哪些数据类型，分别的特点？在你们项目中常见的应用场景有哪些？请列举</font>

​		**String，字符串**，是 redis 的最基本的类型，一个 key 对应一个 value。是二进 制安全的，最大能存储 512MB。

​		 **Hash，散列**，是一个键值(key=>value)对集合。string 类型的 field 和 value 的 映射表，特别适合用于存储对象。每个 hash 可以存储 2^32 -1 键值对（40 多亿）

​		**List，列表**，是简单的字符串列表，按照插入顺序排序。你可以添加一个元素到列 边或者尾部（右边）。最多可存储 232 - 1 元素(4294967295, 每个列表可存储 40 亿) 

​		**Set，集合**，是 string 类型的无序集合，最大的成员数为 232 -1(4294967295, 每 个集合可存储 40 多亿个成员)。 

​		**Sorted set，有序集合**，和 set 一样也是 string 类型元素的集合,且不允许重复的 成员。不同的是每个元素都会关联一个 double 类型的分数。redis 正是通过分数来为集 合中的成员进行从小到大的排序。zset 的成员是唯一的,但分数(score)却可以重复

​		**应用场景：**

​		**计数器**：对 string 进行自增自减运算，从而实现计数器功能。redis 内存型数据库的读写性能非常高，很适合存储频繁读写的计数量。如每日登录次数计数。

​		**热点数据缓存**：将热点数据放到内存中。如首页排行榜数据，具有很大访问频次，使用zset可以实现基于score分数排序；

​		**会话缓存**：用redis统一存储多台应用服务器的会话信息。当应用服务器不再存储用户的会话信息，也就不再具有状态，一个用户可以请求任意一个应用服务器，从而更容易实现高可用性以及可伸缩性。

​		**取数据交集、并集**：基于redis  set 的特性可以对共同好友进行很方便的查询。

​		**分布式事务锁的使用**：基于set lock requestId nx ex time 模式可以很方便编写分布式事务锁

##### 	<font color="red">3、Redis的持久化机制是什么样的？</font>

​		<font color="#ff00dd">1）、什么是RDB？RDB的持久化机制（Save、bgSave）?</font>

​			**RDB**，即 Redis 的内存快照，默认持久化机制，它是在某一个时间点将 Redis 的内存数据**全量**写入一个临时文件，当写入完成后，用该临时文件**替换**上一次持久化生成的文件，这样就完成了一次持久化过程，默认的文件名为**dump.rdb**。

​		<font color="#ff00dd">2）、触发RDB的时间点是什么？</font>三种方式

​			**a、save触发方式**：该命令会阻塞当前Redis服务器，执行save命令期间，Redis不能处理其他命令，直到RDB过程完成为止。

​			**b、bgsave触发方式**：执行该命令时，Redis会在后台异步fork出一个子线程进行快照操作，快照同时还可以响应客户端请求。

​			**c、自动触发**自动触发是由我们的配置文件来完成的。在redis.conf配置文件中，里面有如下配置，我们可以去设置：**save配置** 这里是用来配置触发 Redis的 RDB 持久化条件，也就是什么时候将内存中的数据保存到硬盘。比如“save m n”。表示m秒内数据集存在n次修改时，自动触发bgsave。

​		<font color="#ff00dd">3）、RDB的优缺点分别有哪些？</font>

​			**a、优点：**

​				>由于 RDB 文件是一个非常紧凑的**二进制文件**，所以加载的速度会快于 AOF 方式;

​				>fork 子进程方式，除了fork线程阶段，其他时候不会阻塞;

​				>RDB 文件代表着 Redis 服务器的某一个时刻的全量数据，所以它非常适合做冷备份和全量复制的场景;

​			**b、缺点：**

​				>没办法做到实时持久化，会存在丢数据的风险。定时执行持久化过程，如果在这个过程中服务器崩溃了，则会导致这段时间的数据全部丢失。

​		<font color="#ff00dd">4）、什么是AOF？分为几个阶段？</font>

​		**AOF**，即 append only file，它是将**每一行**对 Redis 数据进行修改的**命令**以独立**日志**的方式**存储起来**。由于 Redis 是将“操作 + 数据” 以格式化的方式保存在日志文件中，他代表了这段时间所有对 Redis 数据的的操作过程，所以在数据恢复时，我们可以直接 replay 该日志文件，即可还原所有操作过程，达到恢复数据的目的。它的主要目的是**解决了数据持久化的实时性**。一共分为**命令写入**、**文件同步**、**文件重写**三个阶段：

​		<font color="#ff00dd">5）、AOF命令同步至日志文件分为哪几种？</font>

| 配置项   | 写回时机     | 优点                         | 缺点                   |
| -------- | ------------ | ---------------------------- | ---------------------- |
| Always   | 同步写回     | 可靠性高，基本上不会丢失数据 | 非常耗性能             |
| Everysec | 每秒写回     | 性能适中                     | 可能会丢失一秒数据     |
| No       | 操作系统控制 | 性能影响小                   | 宕机时数据可能丢失很多 |

​		<font color="#ff00dd">6）、AOF文件重写时间点？重写做了什么？</font>

​			1、**已过期的数据**不在写入文件。			

​			2、**保留最终命令**。例如 set key1 value1 、set key1 value2、....set key1 valuen，类似于这样的命令，只需要保留最后一个即可。

​			3、**删除无用的命令**。例如 set key1 valuel;del key1,这样的命令也是可以不用写入文件中的。

​			4、**多条命令合并成一条命令**。例如 lpush list a、lpush list b、lpush list c，可以转化为 lpush list a b c	

​		<font color="#ff00dd">7）、AOF的优缺点分别有哪些？</font>

​			**a、优点**

​         		> 相比于 RDB，**AOF 更加安全**，**默认同步策略**为 everysec 即**每秒同步一次**，所以顶多我们就失去一秒的数据；

​         		> 根据关注点不同，AOF 提供了不同的同步策略，我们可以根据自己的需求来选择；

​        		> AOF 文件是以 append-only 方式写入，相比如 RDB 全量写入的方式，它**没有任何磁盘寻址的开销，写入性能非常高**；

​             **b、缺点**

​				> 由于 AOF 日志文件是命令级别的，所以相比于 RDB 紧致的二进制文件而言它的加载速度会慢些。

​				> AOF 开启后，支持的写 QPS 会比 RDB 支持的写 QPS 低。

​		<font color="#ff00dd">8）、AOF和RDB同时开启会优先使用哪种进行数据恢复？</font>

​			优先使用AOF,因为AOF数据完整性更高；

​		<font color="#ff00dd">9）、RDB-AOF混合模式是什么？优点有哪些？</font>

​			通过上面的介绍我们知道了 RDB 和 AOF 各有自己的优缺点，选择任意其一都需要接受他的缺点：

​			RDB 能够**快速地存储和恢复数据**，但是在**服务器宕机**时会**丢失大量的数据**，**没有保证**数据的**实时性**和**安全性**；

​			AOF 能够**实时持久化数据**并且**提高了数据的安全性**，但是在**存储和恢复数据方面**又会**消耗大量时间**；

​			Redis 4.0 推出了 **RDB-AOF 混合持久化**方案，该方案是在 **AOF 重写阶段**创建一个**同时包含 RDB 数据**和 **AOF 数据**的 **AOF 文件**，其中 **RDB 数据位于AOF 文件的开头**，他存储了服务器开始执行重写操作时 Redis 服务器的数据状态（RDB 快照方案），**重写操作执行之后的 Redis 命令，则会继续 append 在 AOF 文件末尾**，一般这部分数据都会比较小。这样在 Redis 重启的时候，则可以**先加载 RDB 的内容**，然后**再加载 AOF 的日志内容**，这样**重启的效率**则会得到**很大的提升**，而且由于在运行阶段 Redis 命令都会以 append 的方式写入 AOF 文件，保证了**数据的实时性和安全性**。

##### 	<font color="red">4、Redis主从结构能解决什么问题？</font>

​		解决Redis高可用问题，防止一台服务器宕机，影响整个系统的使用；

##### 	<font color="red">5、Redis主从同步具体流程是什么？ </font>  

​		1）、建立连接

​		2）、数据同步（全量同步、增量同步）【runid运行ID、offset偏移量、复制积压缓冲区】
​			<font color="#ff00dd">1、全量同步具体场景有哪些？流程？如何避免全量同步次数（全量同步非常耗时）</font>

​			主从第一次建立连接时，会执行**全量同步**，将master节点的所有数据都拷贝给slave节点，

​			步骤：

​				1.0、**slave**执行replicaof命令建立连接

​				1.1、**slave**请求数据同步

​				1.2、**master**判断是否是第一次同步

​				1.3、**master**是第一次，返回master的数据版本信息

​				1.4、**slave**保存版本信息

​				2.1、**master**执行bgsave，生成RDB，同时记录RDB期间的所有命令

​				2.2、**master**发送RDB文件给**slave**

​				2.3、**slave**清空本地数据，加载RDB文件

​				3.1、**master**发送repl_baklog中的命令

​				3.2、**slave**执行接收到的命令

​			<font color="#ff00dd">2、增量同步具体场景有哪些？流程？</font>

​			全量同步需要先做RDB，然后将RDB文件通过网络传输个slave，成本太高了。因此除了第一次做全量同步，其它大多数时候slave与master都是做**增量同步**。

​				1.0、slave重启

​				1.1、psync replid offset

​				1.2、判断请求repliid是否一致

​				1.3、不是第一次，回复continue

​				2.1、去repl_baklog中获取offset后的数据

​				2.2、发送offset后的命令

​				2.3、slave执行命令

​		3）、命令传播

##### 	<font color="red">6、如何优化主从同步效率？</font>

​		a、在master中配置repl-diskless-sync yes启用无磁盘复制，避免全量同步时的磁盘IO。

​		b、Redis单节点上的内存占用不要太大，减少RDB导致的过多磁盘IO

​		c、适当提高repl_baklog的大小，发现slave宕机时尽快实现故障恢复，尽可能避免全量同步

​		d、限制一个master上的slave节点数量，如果实在是太多slave，则可以采用主-从-从链式结构，减少master压力

​		1）、从尽量避免全量同步的方面入手（安全重启使runid不发生变化、调大复制积压缓冲区）
​		2）、避免slave从结点太多造成复制风暴（使用树状拓补结构）

##### 	<font color="red">7、Redis的故障恢复依靠什么机制？哨兵机制的主要工作范围、工作流程和作用？</font>

​		RedisTemplate

​		在Sentinel集群监管下的Redis主从集群，其节点会因为自动故障转移而发生变化，Redis的客户端必须感知这种变化，及时更新连接信息。Spring的RedisTemplate底层利用lettuce实现了节点的感知和自动切换。

##### 	<font color="red">8、什么是缓存雪崩？缓存击穿？缓存穿透？分别如何解决？什么是缓存预热？</font>

​	**缓存雪崩：缓存中的数据大量过期，导致大量请求直接访问数据库，解决方案：**

​		1）、缓存数据的过期时间设置随机，防止同一时间大量数据过期现象发生。

​		2）、如果缓存数据库是分布式部署，将热点数据均匀分布在不同的缓存数据库中。

​		3）、允许的话，设置热点数据永远不过期。	

​		4）、要保证redis的高可用，可以使用主从+哨兵或redis cluster，避免服务器不可用；

​		5）、使用redis的持久化RDB+AOF组合策略，防止缓存丢失并且可以快速恢复数据；

​	**缓存击穿：缓存中没有，数据库中有，大量请求直接请求数据库。解决方案：**

​		1）、设置热点数据不过期；

​		2）、第一时间去数据库获取数据填充到redis中，但是这个过程需要加锁，防止所有线程都去读取数据库，一旦有一个线程去数据库获取数据了，其他线程取锁失败后可设置一个合理睡眠时间之后再去尝试去redis中获取数据；

​	**缓存穿透：缓存中没有，数据库中也没有，大量请求直接访问数据库。解决方案**

​		1）、接口层增加校验，如用户鉴权校验，id做基础校验，id<=0的直接拦截；

​		2）、从缓存取不到的数据，在数据库中也没有取到，这时也可以将key-value对写为key-null，缓存有效时间可以设置短点，如30秒（设置太长会导致正常情况也没法使用）。这样可以防止攻击用户反复用同一个id暴力攻击；

​		3）、引入布隆过滤器，过滤一些异常的请求。



##### 	<font color="red">9、Redis是单线程的，为什么读写效率还那么高？</font>

​		a、redis完全基于内存

​		b、数据结构简单

​		c、采用单线程，避免了加锁、释放锁、死锁、线程间切换等消耗

​		d、使用多路I/O复用模型，非阻塞IO

##### 	<font color="red">10、Redis的线程模型是什么样的？（典型的NIO，非阻塞式IO）</font>

​		**Redis 的线程模型**：基于非阻塞的IO多路复用机制的线程模型，**单线程**

​	Redis 是基于 **reactor** 模式开发了**网络事件处理器**，这个处理器叫做**文件事件处理器**（file event handler）。由于这个文件事件处理器是**单线程的**，所以 Redis 才叫做**单线程的模型**。采用 **IO 多路复用机制同时监听多个 Socket**，根据 **socket 上的事件**来选择对应的**事件处理器**来**处理这个事件**。模型如下图：

  ![img](D:\文件\java学习\高频综合面试题汇总\img\redis-202002171001.png)

上图得知，文件事件处理器的结构包含了四个部分：

- **多个 Socket**：客户端发起多个 socket，每个socket 会产生不同的事件，不同的事件对应着不同的操作
- **IO 多路复用程序**：IO 多路复用程序监听着这些 Socket，当这些 Socket 产生了事件，IO 多路复用程序会将这些事件放到一个队列中。
- **文件事件分派器**：通过队列，将事件以有序、同步、每次一个事件的方式向文件时间分派器中传送，文件事件分派器将事件按类型分派给不同的事件处理器进行处理。
- **事件处理器**：分为连接应答处理器、命令请求处理器、命令回复处理器，每个处理器对应不同的 socket 事件。

##### 	<font color="red">11、Redis过期数据的删除策略是什么？有哪些？</font>

​		**定时过期**：每个设置过期时间的key都需要**创建一个定时器**，到过期时间就会**立即清除**。该策略可以**立即清除过期的数**据，**对内存很友好**；但是会**占用大量的CPU资源**去处理过期的数据，从而**影响缓存的响应时间和吞吐量**。

​		**惰性过期**：只有当**访问一个key时**，**才会判断该key是否已过期**，过期则清除。该策略可以**最大化地节省CPU资源**，却**对内存非常不友好**。**极端情况**可能出现**大量的过期key没有再次被访问**，从而不会被清除，**占用大量内存**。

​		**定期过期**：每隔一定的时间，会扫描**一定数量**的**数据库的expires字典**中**一定数量的key**，并清除其中已过期的key。该策略是前两者的一个**折中方案**。通过调整**定时扫描的时间间隔**和**每次扫描的限定耗时**，可以在不同情况下使得CPU和内存资源达到**最优的平衡效果**。

##### 	<font color="red">12、Redis的数据淘汰策略是什么？有哪些？</font>

​		当内存不足时，Redis会根据配置的缓存策略淘汰部分keys，以保证写入成功。当无淘汰策略时或没有找到适合淘汰的key时，Redis直接返回out of memory错误。共有一下六种：

​		1、**volatile-lru（最近最少使用）**：从已设置过期时间的数据集（server.db[i].expires）中挑选最近最少使用的数据淘汰

​		2、**volatile-ttl：**从已设置过期时间的数据集（server.db[i].expires）中挑选将要过期的数据淘汰

​		3、**volatile-random：**从已设置过期时间的数据集（server.db[i].expires）中任意选择数据淘汰

​		4、**allkeys-lru：**从数据集（server.db[i].dict）中挑选最近最少使用的数据淘汰

​		5、**allkeys-random：**从数据集（server.db[i].dict）中任意选择数据淘汰

​		6、**no-enviction（驱逐）**：禁止驱逐数据（新写入的报错）

##### 	<font color="red">13、Redis的慢查询如何排查？</font>

​		Redis 执行命令分为**四个步骤**：发送命令、命令排队、**执行命令**、返回结果。**慢查询只关注步骤 3执行命令 的时间**，**所以没有慢查询并不代表客户端没有超时问题**。

​	Redis 慢查询可通过配置两个参数进行：

- `slowlog-log-slower-than`：设置慢查询预设的超时阈值，单位是微秒

- `slowlog-max-len`：表示慢查询日志存储的条数

  Redis 中有两种修改配置的方法，一种是修改配置文件，另一种是使用 `config set` 命令动态修改：

  ```xml
  config set slowlog-log-slower-than 0
  config set slowlog-max-len 1024
  config rewrite
  ```

  ​	**slowlog-log-slower-than**：默认是 10 毫秒，QPS太小，实际生产建议把这个参数调的更小一些它表示的是慢查询预设的超时阈值。它所阐述的意思是如果某条命令（如 `key *`） 执行”很慢“，执行时间超过了设置的阈值，那么这条命令将会被记录到慢查询日志中。

  ​			 若 `slowlog-log-slower-than = 0`则会记录所有命令

  ​	 		若设置 `slowlog-log-slower-than < 0`，则不会记录任何命令

  ​    **slowlog-max-len**：实际生产中这个参数可以设置得大一些，如1000以上，可以减缓慢查询被剔除的可能Redis 会使用一个列表来存储慢查询日志，`slowlog-max-len` 就是该列表的最大长度。一个命令如果满足慢查询阈值条件则会加入到该列表来，但是如果该列表已经处于最大长度时，那么会删除最开始的一条记录，然后将最新的命令插入到末尾，所以慢查询日志列表是一个**有限的先进先出**列表。

  ​	通过slowlog get [n]命令获取慢查询日志：

  ```sh
  127.0.0.1:6379> slowlog get 1
  1)1) (integer) 3
    2) (integer) 15274630742
    3) (integer) 888
    4) 1) "set"
    	 2) "key1"
    	 3) "value1"
    5) "127.0.0.1:55842"
    6) ""
  ```

  ​	返回的慢查询日志由 4 个属性组成：1、日志的标识 id 	2、发生的时间戳 	3、命令耗时 	4、执行的命令和参数

##### <font color="red">14、分布式锁有哪些实现，你们项目中是怎么实现的？</font>

**1、SETNX + EXPIRE**

**SETNX**：使用`SETNX`命令尝试设置一个键，若键不存在则设置成功并返回1，否则返回0。

**EXPIRE**：设置键的过期时间，防止锁未释放导致死锁。

**问题**：`SETNX`和`EXPIRE`不是原子操作，可能在`SETNX`成功后，`EXPIRE`失败，导致锁无法自动释放

```bash
SETNX lock_key 1
EXPIRE lock_key 10
```

**2、SET with NX and EX**

**SET**：使用`SET`命令的`NX`和`EX`选项，原子性地设置键和过期时间。

**优点**：避免了`SETNX`和`EXPIRE`的非原子性问题。

```bash
SET lock_key 1 NX EX 10
```

**3、Redlock**

- **Redlock**：Redis官方推荐的分布式锁算法，适用于多节点Redis集群。
- **步骤**：
  1. 获取当前时间。
  2. 依次向多个Redis实例请求锁。
  3. 计算获取锁的时间，若在大多数实例上成功且总时间小于锁的有效时间，则获取成功。
  4. 若获取失败，则向所有实例发送释放锁的请求。

**4、Lua脚本**

- **Lua脚本**：通过Lua脚本实现原子操作，确保锁的获取和释放是原子的。
- **优点**：避免竞态条件。

```lua
if redis.call("SETNX", KEYS[1], ARGV[1]) == 1 then
    return redis.call("EXPIRE", KEYS[1], ARGV[2])
else
    return 0
end
```

**5、Redisson**

- **Redisson**：基于Redis的Java客户端，提供分布式锁的实现。
- **特点**：支持可重入锁、公平锁、读写锁等，自动续期，防止锁过期。

```java
RLock lock = redissonClient.getLock("lock_key");
lock.lock();
try {
    // 业务逻辑
} finally {
    lock.unlock();
}
```

### 总结

- **简单场景**：使用`SET with NX and EX`。
- **复杂场景**：使用Redlock或Redisson。
- **高一致性要求**：考虑Zookeeper。



##### 	<font color="red">14、如何正确使用Redis的分布式事务锁？（Zookeeper也可以实现分布式锁）</font>

​		通过set nx上锁方式实现，但是不注意写法很可能会出现很多问题；

​		**错误用法**：先通过setnx上锁，再通过expire设置过期时间，最后执行完任务后手动del释放锁；

​		**场景一问题**（**死锁**）：通过setnx上锁后**出现异常**，导致**无法**去expire**设置锁的过期时间**，更**无法**最后去**手动释放锁**，造成**死锁**！

​		解决：使用上锁最新写法，**保证上锁、设置过期时间**一步完成的**原子性**：**set(lockKey,value,nx,ex,exporeTime);**

​		**场景二问题**（**误删锁**）：**A机器**中**上锁并设置过期时间**完成以后后，系统出现了**阻塞**，导致**锁到了过期时间并自动删除**了，这时**还没有**执行**手动释放锁**的操作，这个时候**B机器上锁成功**，并去执行任务，**任务还未执行完**，**A机器**反应过来了，继续**执行了手动释放锁**的操作，**把B机器**上的**锁给误删了**。

​		解决：上锁同时**加上一个锁id**，如当前线程ID，将**锁id**存入**value**值并记录在变量中，**手动释放锁**的时候比较一下value中的锁id跟变量中id是否一致，也就是**判断一下是否自己还在持有锁**，如果不是，就不执行删除操作了。

​		**场景三问题**（**误删锁**）：这种误删锁是基于场景2**判断锁id**和**释放锁操作**这两步没有保证原子性所导致的。

​					具体为：A机器**带锁id方式取锁、设置过期时间并执行完任务后**，希望通过判断比较锁id之后去释放锁，**判断通过后系统出现阻塞**，阻塞到锁也到了过期时间自动释放了锁，这时还未进行手动释放锁操作，这个时候B机器上锁成功，并去执行任务，**任务还未执行完**，**A机器**反应过来了，继续**执行了手动释放锁**的操作，**把B机器**上的**锁给误删了**。

​		解决：保证**判断锁和释放锁的原子性**：使用redis执行**LUA脚本**，保证**一步执行判断锁和释放锁**。

		String luaScript = 'if redis.call('get', KEYS[1]) == ARGV[1] then return redis.call('del', KEYS[1]) else return 0 end';

​		redisClient.eval(luaScript , Collections.singletonList(key), Collections.singletonList(threadId));

​		**场景四问题（锁续命）**：这种场景是指线程中任务还没执行完，锁就已经到过期时间，这种情况可以给任务执行线程添加守护线程，守护线程负责对锁的expire时间进行监控，每当到过期前一秒就对过期进行判断，如果任务还在进行且锁马上过期，则对过期时间重新进行设置。

​		**综上**：正确使用redis分布式事务锁需要保证两个原子性：

​						1、上锁和设置过期时间需要保证原子性；

​						2、 判断锁ID是否为自己所有和解锁需要保证原子性；

​		**补充**：其实关于上述四个场景的问题，使用redis客户端**Redisson**都能够得到很好的解决，redisson**内部已经实现了上述几点问题的解决机制**，原理同上。

##### 	<font color="red">15、Redis的双写一致性如何保证？</font>

​	 	通常推荐使用先更新数据库 + 再删除缓存这种方案来操作数据库和缓存，但是如果删除缓存失败就会导致数据库和缓存不一致。那如何保证删除一定成功呢？重试 or 异步重试。

​		**1. 重试**

​		保证删除缓存成功是解决一致性的关键，所以失败后可以重试，但是重试也存在一些问题：重试次数设为多少比较合理？重试会一直占用线程资源，所以这种方案不太好。

​		**2. 异步重试**

​		方案一：把重试请求放到消息队列中，由专门的应用来进行重试，直到成功。或者直接把删除缓存这个操作放到消息队列中，消息队列保证消息成功投递，成功消费后才会删除消息，否则还会继续投递消息给消费者（符合重试场景）。
​		方案二：订阅数据库变更日志，再操作缓存。当一条数据发生改变时，MySQL就会产生一条binlog（变更日志），可以订阅这个日志，拿到具体操作的数据，然后再根据这条数据，去删除对应的缓存。订阅变更日志，目前也有比较成熟的开源中间件，例如阿里的canal，可以使用canal将binlog日志采集发送到消息队列里面。

​		**3. 缓存延迟双删**

​		对于Redis读写分离 + 主从复制延迟，以及先删除缓存，再操作数据库这两种情况导致的数据不一致性，可以采用缓存延时双删策略（先删除缓存，再更新数据库，休眠一会，再次删除缓存）来解决，但是延迟时间设置多久才合适？第一种情况延迟时间要大于主从复制的延迟时间；第二种情况延迟时间要大于第二个线程读取数据+写入缓存的时间，这在实际场景中不好评估。

##### 	<font color="red">16、项目搭建多级缓存的好处是什么？实现多级缓存的流程是什么？（加分项）</font>

​		**多级缓存**就是充分利用请求处理的每个环节，**分别添加缓存，减轻Tomcat压力**，提升服务性能：

​			1、浏览器访问静态资源时，优先读取**浏览器本地缓存**

​			2、访问非静态资源（ajax查询数据）时，访问服务端

​			3、请求到达Nginx后，优先读取**Nginx本地缓存**

​			4、如果Nginx本地缓存未命中，则去直接**查询Redis（不经过Tomcat）**

​			5、如果Redis查询未命中，则**查询Tomcat**

​			6、请求进入Tomcat后，优先查询**JVM本地进程缓存（如Caffeine）**

​			7、如果JVM进程缓存未命中，则**查询数据库**

##### 	<font color="red">17、Redis的hash槽一共有多少个？数据是如何进行入槽的？如果实现动态扩容？</font>

​		

​										消费者	
​	生产者 -> 【exchange -> queue】  -> 消费者（开启多个线程）
​										消费者
​	

# 七、MQ

## 1、Rabbitmq

##### 	<font color="red">1、Rabbitmq消息模式有哪些？你们用的哪种？（5种）</font>

​		a.基本消息队列（BasicQueue）

​		b.工作消息队列（WorkQueue）

​		c.发布订阅（Publish、Subscribe）根据交换机的不同分为三种：

​				Fanout Exchange：广播

​				Direct Exchange：路由

​				TopicExchange：主题

​	我们基本上使用主题，因为主题可以实现上面所有的功能；

##### 	<font color="red">2、Rabbitmq如何保证mq消息可靠性？（3大方面）</font>

​		1、如何保证生产者不丢

​			publisher-confirm，发送者确认：

​					1.消息成功投递到交换机，返回ack 

​					2.消息未投递到交换机。返回nack

​			publisher-return，发送者回执：消息投递到了交换机，但没有路由到队列。返回ACK和路由失败的原因，如果成功没得返回；**确认机制发送消息时，需要给每个消息设置一个全局唯一id，以区分不同消息，避免ack冲突；**

​		2、如何保证消息到达MQ了之后不丢

​			**开启交换机持久化，队列持久化，消息持久化**

​		3、如何保证消费者不丢

​			RabbitMQ是通过消费者回执来确认消费者是否成功处理消息的：消费者获取消息后，应该向RabbitMQ发送ACK回执，表明自己已经处理消息。

​		4、开启消费者失败重试机制，并设置MessageRecoverer，多次重试失败后将消息投递到异常交换机，交由人工处理

##### 	<font color="red">3、Rabbitmq如何实现延时消息？（2种）</font>

​		死信交换机

​		延迟交换机插件

​		

##### 	<font color="red">4、什么是死信队列？什么样的消息会进入死信队列？</font>

​		

##### 	<font color="red">5、Rabbitmq如何解决消息堆积问题？（3种思路）</font>

​		1、增加消费者

​		2、提高消费者消费速度（开启多线程消费）

​		3、扩大队列容量（惰性队列）

##### 	<font color="red">6、如何保证消息的幂等性？（从业务层面进行判断）</font>

​		**消息的幂等性：**就是即使多次收到了消息，也不会重复消费。所以保证消息的幂等性就是保证消息不会重复消费，这在开发中是很重要的。比如客户点击付款，如果点击了多次，那也只能扣一次费。

​		**1、保证生产者不重复发送消息到MQ**

​			mq内部可以为每条消息生成一个全局唯一、与业务无关的消息id，当mq接收到消息时，会先根据该id判断消息是否重复发送，mq再决定是否接收该消息。

​		**2、保证消费者不重复消费**

​			 消费者怎么保证不重复消费的关键在于消费者端做控制，因为MQ不能保证不重复发送消息，所以应该在消费者端控制：即使MQ重复发送了消息，消费者拿到了消息之后，要判断是否已经消费过，如果已经消费，直接丢弃。所以根据实际业务情况，有下面几种方式：

​			1、如果从MQ拿到数据是要存到数据库，那么可以根据数据创建唯一约束，这样的话，同样的数据从MQ发送过来之后，当插入数据库的时候，会报违反唯一约束，不会插入成功的。（或者可以先查一次，是否在数据库中已经保存了，如果能查到，那就直接丢弃就好了）

​			2、让生产者发送消息时，每条消息加一个全局的唯一id，然后消费时，将该id保存到redis里面。消费时先去redis里面查一下有么有，没有再消费。（其实原理跟第一点差不多）。

​			3、如果拿到的数据是直接放到redis的set中的话，那就不用考虑了，因为set集合就是自动有去重的。

##### 	<font color="red">7、如何保证消息顺序消费</font>

​		1）、让同一组消息有序的存入同一个队列  
​		2）、同一个队列只能有一个消费者进行消费
​		3）、引出的问题：如何保证消息消费的速度
​			1）、可以起多个队列去存放这一类消息
​			2）、消费者中消费消息的代码可以开启多个线程，一个线程消费一个List

## 1、Kafka

##### <font color="red">1、如何保证消息的幂等性？（从业务层面进行判断）</font>





# 八、微服务

## 1、概念问题

##### 		<font color="#ff00ff">1）、什么是微服务？解决微服务各种问题都用了哪些组件？</font>

​			注册中心（服务发现问题）：Netflix Eureka、Alibaba Nacos、Consul

​			远程调用（服务调用问题）：Dubbo、Feign

​			配置中心（配置管理问题）：SpringColudConfig、Alibaba Nacos

​			网关服务（请求路由问题）：SpringCloudGateway、zuul

​			服务监控以及保护问题：Hystix、Sentinel

​			分布式事务：Seata

##### 		<font color="#ff00ff">2）、架构演变，什么是单体架构？什么是分布式架构？什么是微服务架构？</font>

​		**1、单体架构：**  

​			项目功能简单, 一个项目只需一个应用, 将所有功能部署在一起, 这样的架构好处是减 少了部署节点和成本

​		缺点: 代码耦合，开发维护困难, 无法水平扩展, 单点容错率低，并发能力差

​		**2、垂直拆分架构**

​			当访问量逐渐增大，单一应用无法满足需求，此时为了应对更高的并发和业务需求，我 们根据业务功能对系统进行拆分

​			优点：

​				系统拆分实现了流量分担，解决了并发问题

​				可以针对不同模块进行优化, 方便水平扩展，负载均衡，容错率提高

​			缺点：

​				系统间相互独立，会有很多重复开发工作，影响开发效率

​		**3、分布式服务**

​			当垂直应用越来越多, 随着项目业务功能越来越复杂, 并非垂直应用这一条线进行数据 调用, 应用和应用之间也会互相调用, 也就是完成某一个功能,需要多个应用互相调用, 这就 是将功能拆完来完成的分布式架构。

​			优点: 将基础服务进行了抽取，系统间相互调用，提高了代码复用和开发效率 

​			缺点: 系统间耦合度变高，调用关系错综复杂，难以维护.

​		**4、服务治理架构 SOA(面向服务的架构)**

​			当服务越来越多，容量的评估，小服务资源的浪费等问题逐渐显现，此时需增加一个调 度中心基于访问压力实时管理集群容量，提高集群利用率。此时，用于提高机器利用率的资 源调度和治理中心(SOA)是关键, 而最初的服务治理基石是 Dubbo 服务治理

​			以前**分布式服务**出现的问题：

​				1、服务越来越多，需要管理每个服务的地址, 调用关系错综复杂，难以理清依赖关系

​				2、服务过多，服务状态难以管理，无法根据服务情况动态管理

​			**SOA 服务治理架构的优点:**

​				1、服务注册中心，实现服务自动注册和发现，无需人为记录服务地址

​				2、服务自动订阅，服务列表自动推送，服务调用透明化，无需关心依赖关系

​				3、动态监控服务状态监控报告，人为控制服务状态

​			**SOA 服务治理架构的缺点：**

​				1、服务间依然会有依赖关系，一旦某个环节出错会影响较大(容错机制)

​				2、服务关系复杂，运维、测试部署困难，不符合开发-运维一站式维护的思想.

​		**5、微服务**

​			前面说的 SOA，英文翻译过来是面向服务。微服务，似乎也是服务，都是对系统进行 拆分。因此两者非常容易混淆，但其实却有一些差别：

​			**微服务的特点：**

​				**单一职责：**微服务中每一个服务都对应唯一的业务能力，做到单一职责. 

​				**微：**微服务的服务拆分粒度很小，例如一个用户管理就可以作为一个服务。每个服 务虽小，但“五脏俱全”。

​				**面向服务：**面向服务是说每个服务都要对外暴露 Rest 风格服务接口 API。并不关心 服务的技术实现，做到与平台和语言无关，也不限定用什么技术实现，只要提供 Rest 的接口即可。 

​				**自治：**自治是说服务间互相独立，互不干扰

​					 **团队独立：**每个服务都是一个独立的开发团队，人数不能过多。 

​					**技术独立：**因为是面向服务，提供 Rest 接口，使用什么技术没有别人干涉 

​					**前后端分离：**采用前后端分离开发，提供统一 Rest 接口，后端不用再为 PC、 移动段开发不同接口 

​					**数据库分离：**每个服务都使用自己的数据源 

​					**部署独立：**服务间虽然有调用，但要做到服务重启不影响其它服务。有利于持 续集成和持续交付。每个服务都是独立的组件，可复用，可替换，降低耦合， 易维护. 基于 docker 容器是开发.

​			目前微服务微服务架构主流的是 **SpringBoot+Dubbo** 和 **SpringBoot+SpringCloud** 的架构模式. 

​			综上, 无论是 **SOA** 还是**微服务**, 都需要进行服务调度, 目前主流的服务调度室 RPC 和 HTTP 两种协议, 而 Dubbo 基于 RPC 的远程调度机构, SpringCloud 是基于 Rest 风格(基于 http 协议实现的)的 Spring 全家桶微服务服务治理框架（ 说到这里也可以继续说下 Dubbo 和 SpringCloud 的区别）

##### 		<font color="#ff00ff">3）、微服务有哪些特点？</font>





## 2、远程调用

##### 	<font color="#ff00ff">1）、什么是Feign，用来做什么的？Feign底层调用是怎么实现的？底层协议是什么？优势是什么？</font>

​		**Feign**是一种负载均衡的HTTP客户端, 使用Feign调用API就像调用本地方法一样，从避免了调用目标微服务时，需要不断的解析封装json 数据的繁琐。Feign集成了Ribbon。Ribbon+eureka是面向微服务编程，而Feign是面向接口编程。

​			Fegin是一个声明似的web服务客户端，它使得编写web服务客户端变得更加容易。使用Fegin创建一个接口并对它进行注解。它具有可插拔的注解支持包括Feign注解与JAX-RS注解，Feign还支持可插拔的编码器与解码器，Spring Cloud 增加了对 Spring MVC的注解，Spring Web 默认使用了HttpMessageConverters, Spring Cloud 集成 Ribbon 和 Eureka 提供的负载均衡的HTTP客户端 Feign

##### 	<font color="#ff00ff">2）、服务间调用，其中一个服务宕机了，这个时候怎么做呢？</font>

​		服务降级，让服务走降级逻辑

##### 	<font color="#ff00ff">3）、Ribbon是什么？负载均衡策略有哪些？底层原理是什么？默认是哪种？</font>

​		 **Ribbon** 是 Netflix 发布的云中服务开源项目，给客户端提供负载均衡, 也就是说 Ribbon 是作用在消费者方的。简单来说, 它是一个客户端负责均衡器, 它会自动通过某种算法去分配你要连接的机 器.

​		 **1、线性轮询策略： RoundRibbonRule（默认）**

​			BaseLoadBalancer 负载均衡器默认采用线性负载轮询负载均衡策略。**工作流程**：RoundRibbonRule 类的 choose(ILoadBalancer Ib,Object key) 方法初始化一个计数器。incrementAndGetModulo() 方法获取一个下标 (是先加1，然后和服务清单总数取模获取到的，不会越界)，是一个不断增长的数。chooseServer(Object key) 方法拿着下标去服务列表中获取服务，每次循环计数器都会加1。如果连续10次都没有取到服务，则会报 “No available alive servers after 10 tries from loadbalancer.” 警告。

​		**2、重试策略：RetryRule**

​		重试策略在使用 RetryRule 类中定义的 choose(ILoadBalance Ib,Object key) 方法来选择一个服务实例。choose() 方法也是采用 RoundRibbonRule 中的 choose() 方法来选择一个服务实例的。**工作流程**：如果选择到的服务实例正常，则返回数据。如果选择到的服务实例为 null 或 失效，则 choose() 方法会在失效时间前不断地进行重试。如果超过了失效时间还是没有取到，则返回一个 null。

​		**3、加权响应时间策略：WeightedResponseTimeRule**

​		WeightedResponseTimeRule 类是 RoundRibbonRule 的一个子类，它对 RoundRibbonRule 的功能进行了扩展。它根据每一个服务实例的运行情况先计算出该服务实例的一个权重，然后根据权重进行服务实例的挑选，这样能够调用到更优的服务实例。**工作流程：**每 30S 计算一次各服务实例的响应时间，以响应时间来计算权重。平均响应时间越短则权重越高，权重越高则被选中的的概率越高，反之则被选中的概率较低。WeightedResponseTimeRule 中有一个名叫 DynamicServerWeightTask 的定时任务。它是一个后台线程，定期从 status 里面读取响应时间，用来计算每个服务实例权重。

​		**4、随机策略：RandomRule**

​		随机选择一个可用的服务实例。**工作流程：**负载均衡通过 upList() 和 allList() 方法获得可用服务实例列表，然后初始化了一个 Randow 对象以生成一个不大于服务实例总的随机数。choose() 方法将该随机数作为下标获取一个服务实例。轮询 “index” 选择 “index” 对应的服务实例。

​		**5、客户端配置启动线性轮询策略：ClientConfigEnabledRoundRobbinRule**

​		继承该策略默认的 choose() 方法就能实现线性轮询机制。

​		**6、最空闲策略：BestAvailableRule**

​		该服务是逐个考察各服务实例，然后选择一个最小的并发请求的服务实例来提供实例。BestAvailableRule 继承自 ClientConfigEnabledRoundRobbinRule 类。**工作流程：**根据在 loadBalancerStats() 方法中保存的服务实例的状态信息来过滤失效的服务实例。判断 loadBalancerStats 是否为空。如果 loadBalancerStats 不为空，则找出并发请求最小的服务实例来使用。如果 loadBalancerStats 为空，则 BestAvailableRule 类将采用它的父类。即 ClientConfigEnabledRoundRobbinRule 的服务选取策略 (线性策略)。

##### 	<font color="#ff00ff">4）、Ribbon是如何实现轮询的？如果让你自己实现轮询，如何实现？</font>	

​		**普通轮询：**

​			1、如果服务器当前权重值为空，给三台服务器设置默认权重值为：3、2、1

​			2、每次从三台服务器挑选当前权重值最大的那个来处理请求，并且当前权重值 - （服务器数量-1）

​			3、其他服务器当前权重值+1	

​		**加权轮询：**

​			1、如果服务器当前权重值为空，给三台服务器设置当前权重值为：0，且为每台机器加上固定权重值

​			2、每次从三台服务器挑选当前权重值最大的那个来处理请求，并且当前权重值 - （固定权重值之和）

​			3、为每台机器当前权重值加上固定权重值F

##### 	<font color="#ff00ff">5）、Feign和Ribbon的关系是什么？</font>

​		Ribbon是一个基于Http和TCP客户端的负载均衡工具，

​		Feign是在Ribbon的基础上做了改进，是一个使用起来更加方便的Http客户端，采用接口方式，将需要调用的服务定长成抽象接口，不需要自己构建Http请求

##### 	<font color="#ff00ff">6）、你们项目中如何使用Feign的（Feign的最佳实践）</font>

​		最佳实现由两种，继承和抽取

​		继承：不推荐，定义一个API接口，利用定义方法，并基于Spring'MVC注解做声明，Feign客户端和Controller都集成该接口，不过缺点太明显，服务提供方和消费方紧密耦合，而且参数列表中的注解映射并不会继承

​		抽取：推荐，将Feign的Client抽取为独立模块，并且把接口有关的的POJO，默认的Feign配置都放在这个模块中，给所有消费者使用

##### 	<font color="#ff00ff">7）、Feign远程调用时的日志级别有哪些？</font>

​		NONE：不记录任何日志信息，这是默认值。

​		BASIC：仅记录请求的方法，URL以及响应状态码和执行时间

​		HEADERS：在BASIC的基础上，额外记录了请求和响应的头信息

​		FULL：记录所有请求和响应的明细，包括头信息、请求体、元数据。

##### 	<font color="#ff00ff">8）、如何优化Feign的调用性能？</font>

​		1：日志级别尽量用Basic

​		2：使用HttpClient或OKHttp代替URLConnection（这个URLConnction是默认实现，不支持连接池）

##### 	<font color="#ff00ff">7）、Feign的默认超时时间是多久？重试次数是几次？</font>

​		超时时间是一秒，重试是一次

##### 	<font color="#ff00ff">8）、Dubbo服务注册与发现的原理？（官方原理图）</font>

​		内部结构角色：服务提供者，注册中心，服务消费者，监控中心，运行容器

​		Consumer：调用远程服务的服务消费者

​		Registry：服务注册与发现的注册中心

​		Provider：暴露服务的提供方

​		Monitor：统计服务和调用次数和调用时间的监控中心

​	流程：

​		服务容器负责启动，加载，运行provider

​		provider在启动时，向registry注册自己提供的服务

​		Consumer在启动时，向registry订阅自己所需要的服务

​		registry返回provider地址给Consumer，Consumer会保存地址列表，如果有更变registry将基于长连接推送变更数据给Consumer

​		Consumer从privider提供的地址列表中，基于自己的负载均衡算法，选一台进行调用，如果调用失败，再选另一台

​		Consumer和provider，在内存中调用的次数和时间，定时每分钟发送一次统计数据给monitor

​    ![0](https://note.youdao.com/yws/public/resource/05a9ab7d3dbc8584b065d13f768a2b6c/xmlnote/WEBRESOURCE24547c31e901e29265d0d7863a8451cb/8473)

##### 	<font color="#ff00ff">9）、Dubbo负载均衡策略有哪些？默认是哪种？</font>

​		 random ：按权重随机，默认值。按权重设置随机概率。（默认）

​		roundrobin ：按权重进行轮询调用。

​		leastActive：最少活跃调用数，Dubbo认为活跃度最小的性能会更高，而相同活跃数进行随机调用。

​		 consistentHash：一致性 Hash，相同参数的请求总是发到同一提供者。

##### 	<font color="#ff00ff">10）、Dubbo支持哪些通信协议？默认是哪种？一般用哪种协议？有什么好处？</font>

​		dobbo协议，rmi协议，webserver协议，http协议，hession协议，thrift协议，memache，redis，rest协议

​		默认是dobbo协议

​		**好处：**适合大并发小数据量的服务调用，以及服务消费者远大于服务提供者的情况，缺点是不适合传送大数据包服务

##### 	<font color="#ff00ff">11）、注册中心挂了影响服务调用吗？为什么？</font>

​		不会，会继续通信，注册中心全部宕机，会依靠本地缓存通讯

##### 	<font color="#ff00ff">12）、Dubbo启动检查如何设置？多版本支持如何设置？</font>

​		启动检测设置：在yml里面配置，consumer：check=false 是关闭

​		多版本设置：在服务实现类的@DubboService注解上指定版本 version=”版本号“

​                     		  在消费者调用时@DubboReference后指定版本version=”版本号“

##### 	<font color="#ff00ff">13）、Dubbo的默认超时时间是多久？重试次数是几次？</font>

​		超时时间一秒，重试次数两次

##### 	<font color="#ff00ff">14）、Dubbo进行服务注册和发现的核心注解是哪个？</font>

​		服务注册@DubboService   服务发现@DubboReference

##### 	<font color="#ff00ff">15）、Dubbo服务如何进行监控和管理？</font>

​		在gitHub上下载Dubbo-admin

##### 	<font color="#ff00ff">16）、Spring Cloud 和Dubbo的区别</font>

​		底层协议：springcloud基于合同谈判协议，dubbo基于Tcp协议，决定了dubbo的性能会比spring cloud好

​		注册中心：Spring Cloud使用的是eureka,dubbo推荐使用zookeeper

​		模型定义：dubbo将接口定义为一个服务，Spring Cloud则是将一个应用定义为一个服务

​		SpringCloud是一个生态，而Dubbo是SpringCloud生态中的一个关于服务调用的一种解决方案（服务治理）

## 3、注册中心

##### 	<font color="red">1）、Eureka</font>

​		<font color="#ff00ff">1、eureka是属于什么体系的技术（）</font>

​			Spring Cloud体系

​		<font color="#ff00ff">2、eureka技术体系有哪些角色？</font>

​			服务端用作注册中心，客户端用作微服务

​		<font color="#ff00ff">3、eureka的自我保护机制是什么？什么时候开启？为什么开启？开启了会发生什么？</font>

​			**自我保护机制**：为了防止当微服务状态正常，网络分区故障，导致实例被误杀而提供的一种保护机制

​			**什么时候开启**：Eureka server 在运行期间会去统计心跳失败比例在15分钟内是否低于85%，如果低于85%，Eureka server则会进入自我保护机制

​			**开启了会发生什么：**

​				1）Eureka不再从注册列表中移除因为长时间没收到心跳而应该剔除的服务

​                2）Eureka仍然会接收新服务的注册和查询，但是不会同步到其他节点上，保证当前节点依然可用

​                3）当网络稳定时，当前实例新的注册消息会被同步到其他节点中

​		<font color="#ff00ff">4、eureka作为注册中心的原理是什么？心跳检测某个服务是否健康的原理详细说下？</font>

​			**原理**：Eureka server主要对外提供三个功能

​			**服务注册：**服务提供者启动时，会通过Eureka Client向Eureka Server注册消息，Eruka Server会储存该服务的信息，内部有两层缓存机制来维护整个注册表

​			**提供注册表：**服务消费者在调用服务时，如果Eureka Client没有缓存注册表的话，会从Eureka Server获取最新的注册表

​			**同步状态**：Eureka Client通过注册，心跳机制，和Eureka Server同步当前客户端的状态

​		<font color="#ff00ff">5、eureka集群是属于AP还是CP？</font>

​			**AP**， eureka在设计时的分区容错保证了eureka各个节点都是平等的，只要不是所有节点都挂掉eureka就可以正常注册与使用，不会像zk出现选举而短暂不可用的情况。

##### 	<font color="red">2）、Nacos</font>

​		<font color="#ff00ff">1、nacos是属于什么体系的技术？</font>

​			**Spring Cloud Alibaba**

​		<font color="#ff00ff">2、nacos作为注册中心的原理是什么？</font>	

​		大致原理：**服务注册与发现**是[微服务](https://so.csdn.net/so/search?q=微服务&spm=1001.2101.3001.7020)架构得以运转的核心功能，它不提供任何业务功能，仅仅用来进行服务的发现和注册，并对服务的健康状态进行监控和管理。其核心的工作原理：

​			服务提供者注册信息到注册中心上；

​			服务消费者通过注册中心获取服务地址列表；

​			注册中心动态感知服务的上线与下限(心跳)；

​			服务列表变化通知（pull、push）；

​		**Nacos注册中心原理**

​		https://blog.csdn.net/qq_33375499/article/details/125710182

​		1、Nacos为服务注册与发现提供了一个SDK类 NamingService，通过该类，可以实现服务的注册与发现、订阅服务的动态变化、获取服务实例、获取注册中心的健康状态等等。创建 NamingService：NamingService namingService = NacosFactory.createNangService(properties);获取 NacosNamingService 中带[Properties](https://so.csdn.net/so/search?q=Properties&spm=1001.2101.3001.7020)形参的构造函数，然后反射创建。

<details>
<summary>	其中，NamingService中的接口，可以分为以下几类：</summary>
    <li>	namingService.registerInstance()：注册实例</li>
    <li>	namingService.deregisterInstance()：取消注册</li>
    <li>	namingService.getAllInstances(String serviceName)：获取服务的所有实例</li>
    <li>	namingService.getServicesOfServer(int pageNo, int pageSize)：分页查询，从服务器获取所有服务名称</li>
    <li>	namingService.getSubscribeServices()：获取当前客户端所有订阅的服务</li>
    <li>	namingService.selectInstances()：根据条件获取服务实例</li>
    <li>	namingService.selectOneHealthyInstance()：根据条件选择一个健康的实例</li>
    <li>	namingService.subscribe()：订阅服务以接收实例更改事件</li>
    <li>	namingService.unsubscribe()：取消订阅</li>
    <li>	namingService.getServerStatus()：获取服务器健康状态</li>
</details>

​		2、通过[构造函数](https://so.csdn.net/so/search?q=构造函数&spm=1001.2101.3001.7020)，创建一个NacosNamingService 对象

​			创建服务代理类：用于服务实例注册/注销、心跳发送、服务实例获取、服务实例更新/删除/创建等。

​			所有向服务器发送、获取的动作，都在 NamingProxy 中完成。

​			BeatReactor类 主要是用来发送心跳包，服务端根据心跳时间，来判断当前服务上线、下线。

​			HostReactor用于获取服务端注册信息，故障转移，定时刷盘备份等。

​		3、

​		<font color="#ff00ff">3、nacos如何确定唯一的一个服务?（通过namespace、group、service、集群唯一确定一个服务）</font>

​			Nacos提供了**namespace(命名空间)来实现环境隔离**，Nacos中可以有多个namespace，**namespace下可以有group(分组)，service(服务名)等，不同namespace之间相互隔离**

​		<font color="#ff00ff">4、nacos中namespace、group分别的作用是什么？</font>

​			**命名空间（Namespace）:Nacos服务中最顶层、也是包含范围最广的概念，用于强制隔离类似环境或者租户等场景。Nacos的服务也需要使用命名空间来进行隔离。**

​			**用法：**命名空间默认为public，在项目开发中，如果不指定命名空间，那么会使用默认值public。**官方推荐使用运行环境来定义命名空间**，如生产版本可使用public，开发版可定义为private。在项目开发中，可通过配置"spring.cloud.nacos.discovery.namespace"老定义命名空间。

​			**分组名（Group）：**Nacos中次于命名空间的一种隔离概念，区别于命名空间的强制隔离属性，分组属于一个弱隔离概念，主要用于逻辑区分一些服务使用场景或不同应用的同名服务，用常用的情况主要是同一个服务的测试分组和生产分组、或者将应用名作为分组以防止不同应用提供的服务重名。

​		<font color="#ff00ff">5、nacos和eureka的异同有哪些？</font>

​			共同点：**都支持服务注册，服务拉取，服务提供者心跳方式做健康检测**

​			不同点：**Nacos支持服务端主动提供检测提供者状态**，**临时实例采用心跳检测模式，非临时实例采用主动检测模式**

​              			**Nacos临时实例心跳不正常会被剔除，而非临时实例不会**

​             			 Nacos支持服务列表变更的消息推送模式，服务列表更新更及时

​              			**Nacos集群默认采用AP模式**，**当集群中存在非临时实例时，采用CP模式**。**Eureka采用AP模式**

​		<font color="#ff00ff">6、nacos的临时节点和非临时节点有什么区别？</font>

​			**临时实例**只是临时存在于注册中心中，会在服务下线或不可用时被注册中心剔除，临时实例会与注册中心保持心跳，注册中心会在⼀段时间没有收到来自客户端的心跳后会将实例设置为不健康，然后在⼀段时间后进行剔除。

​			**永久实例**在被删除之前会永久的存在于注册中心，且有可能并不知道注册中心存在，不会主动向注册中心上报心跳，那么这个时候就需要注册中心主动进行探活。

​		<font color="#ff00ff">7、nacos集群是属于AP还是CP？(AP或CP)</font>

​			一致性(Consistency,C)、可用性(Availability,A)、分区容错性(Partition Tolerance, P)三者不可兼得。

​			**Nacos支持CP+AP模式**，即Nacos可以根据配置识别为CP模式或AP模式，默认是AP模式。如果注册Nacos的client节点注册时ephemeral(临时节点)=true，也就是说存在临时节点的话，那么Nacos集群对这个client节点的效果就是AP，采用distro协议实现；而注册Nacos的client节点注册时ephemeral（临时节点）=false，那么Nacos集群对这个节点的效果就是CP（强一致性）的，采用raft协议实现。根据client注册时的属性，AP，CP同时混合存在，只是对不同的client节点效果不同。Nacos可以很好的解决不同场景的业务需求。

​		<font color="#ff00ff">8、nacos的健康检查机制</font>

​		分为两种模式：1 agent上报模式，2 服务端主动检测

​		**1、 agent上报模式**
​			客户端（注册在nacos上的其它微服务实例）健康检查。

​			客户端通过心跳上报方式告知服务端(nacos注册中心)健康状态；

​			默认心跳间隔5秒；

​			nacos会在超过15秒未收到心跳后将实例设置为不健康状态；

​			超过30秒将实例删除；

​		**2 、服务端主动检测**
​			服务端健康检查。

​			nacos主动探知客户端健康状态，默认间隔为20秒；

​			健康检查失败后实例会被标记为不健康，不会被立即删除。

​		<font color="#ff00ff">9、为什么会有两种健康检查模式呢？</font>

​		对于**临时实例**，健康检查失败，则直接可以从列表中删除。这种特性就比较适合那些需要应对流量突增的场景，服务可以进行弹性扩容。当流量过去之后，服务停掉即可自动注销了。

​		对于**持久化实例**，健康检查失败，会被标记成不健康状态。它的好处是运维可以实时看到实例的健康状态，便于后续的警告、扩容等一些列措施。

##### 	<font color="red">3）、Zookeeper</font>

​		<font color="#ff00ff">1、Zookeeper的内部结构是什么？</font>



​		<font color="#ff00ff">2、使用Zookeeper作为分布式事务锁的原理是什么？</font>

​		分布式锁使用的是 Zookeeper 的临时有序节点 

​		**需求:** 在分布式系统中, 很容出现多台主机操作同一资源的情况, 比如两台主机同 时往一个文件中追加写入文本, 如果不去做任何的控制, 很有可能出现一个写入操 作被另一个写入操作覆盖掉的状况. 

​		**方案:** 此时我们可以来一把锁, 哪个主机获取到了这把锁, 就执行写入, 另一台主 机等待; 直到写入操作执行完毕，另一台主机再去获得锁，然后写入. 这把锁就称为分布式锁, 也就是说:**分布式锁是控制分布式系统之间同步访问共享 资源的一种方式** 

​		**实现:** 使用 Zookeeper 的临时有序节点可以轻松实现这一需求. 

​			1、所有需要执行操作的主机都去 Zookeeper 上创建一个临时有序节点.

​			2、 然后获取到 Zookeeper 上创建出来的这些节点进行一个从小到大的排序. 

​			3、判断自己创建的节点是不是最小的, 如果是, 自己就获取到了锁; 如果不是, 则对最小的节点注册一个监听. 

​			4、如果自己获取到了锁, 就去执行相应的操作. 当执行完毕之后, 连接断开, 节 点消失, 锁就被释放了.

​			5、如果自己没有获取到锁, 就等待, 一直监听节点是否消失，锁被释放后, 再重 新执行抢夺锁的操作.

​		<font color="#ff00ff">3、Zookeeper集群属于AP还是CP？(CP强一致性)</font>

​			**zookeeper选择优先保证一致性**。zookeeper保证访问请求都能保持一致的结果，同时具有容错性，但是不保证每次访问请求都是可用的。为什么不保证对请求可用呢？当zookeeper的master节点如果因为网络故障导致与其它节点失去联系时，剩余的节点会进行选举产生新的master节点，但是在这过程需要一定的时间，并且在选举这段时间内，整个zookeeper集群是不可用的。并且由于网络问题，这种情况发生的概率是比较大的。

## 4、配置中心

##### 	<font color="#ff00ff">1）、实现配置中心都可以使用哪些技术？</font>

​		Spring-Cloud-Config，Nacos

##### 	<font color="#ff00ff">2）、使用nacos作为配置中心，如何实现热更新？</font>

​			方式一：在@value注入的变量所在类添加**@RefreshScope**

​			方式二：使用**@ConfigurationProperties**注解代替@Value

##### 	<font color="#ff00ff">3）、nacos作为配置中心，为什么需要用到bootstrap文件？</font>

​			微服务拉取Nacos管理的配置，并且与本地的Application.yml配置合并，才能完成项目的启动，如果尚未读到Application.yml，又如何得知Nacos地址呢，所以spring引入了一个新的配置文件，**bootstrap，这个文件会在Application之前读取**

##### 	<font color="#ff00ff">4）、远程配置文件和本地配置文件属性加载优先级是什么样的？</font>

​		远程带环境的配置>远程共享配置>本地配置

![0](https://note.youdao.com/yws/public/resource/05a9ab7d3dbc8584b065d13f768a2b6c/xmlnote/WEBRESOURCE011fbca3748af0f8c3b38db21d221b63/8251)

​			1、若application.yml 和bootStrap.yml 在同一目录下，则bootStrap.yml 的加载顺序要高于application.yml,即bootStrap.yml  会优先被加载。

​			原理：bootstrap.yml 用于应用程序上下文的引导阶段。

​						bootstrap.yml 由父Spring ApplicationContext加载。

​						bootstrap.yml 可以理解成系统级别的一些参数配置，这些参数一般是不会变动的。

​						application.yml 可以用来定义应用级别的，如果搭配 spring-cloud-config 使用 application.yml 里面定义的文件可以实现动态替换。

​			2、不同位置的配置文件的加载顺序：

​			在不指定要被加载文件时，默认的加载顺序：由里向外加载，所以最外层的最后被加载，会覆盖里层的属性(参考官网介绍)

SpringApplication will load properties from application.properties files in the following locations and add them to the Spring Environment:

​				A /config subdirectory of the current directory.    //位于与jar包同级目录下的config文件夹，

​				The current directory                             //位于与jar包同级目录下

​				A classpath /config package          //idea 环境下，resource文件夹下的config文件夹

​				The classpath root                                //idea 环境下，resource文件夹下  (1->4, 外->里)

​				The list is ordered by precedence (properties defined in locations higher in the list override those defined in lower locations).

##### 	<font color="#ff00ff">5）、使用配置中心的好处是什么？能解决什么问题？</font>

​		如果没有配置中心，将会出现很严重的问题

​			1、**安全性**：配置跟随源代码保存在代码块中，容易造成配置泄漏

​			2、**时效性**：修改配置，需要重启服务器才能生效

​			3、**局限性：**无法动态调整，如日志开关，功能开关

​		有了配置中心之后这些问题都能解决

## 5、服务保护

##### 	<font color="#ff00ff">1）、Hystrix</font>

​		1、hystrix是属于什么体系的技术？（SpringCloud）

​		2、hystrix可以用来干嘛？（服务熔断降级）

​		3、hystrix默认的触发熔断策略是什么？（5分钟之内服务调用异常比例达到一半或者失败次数超过20次）

​		4、hystrix的隔离是基于什么？（线程池隔离【低扇出】）

##### 	<font color="#ff00ff">2）、Sentinel</font>

​		<font color="red">1、sentinel可以用来干嘛？（限流、隔离、熔断、降级）</font>

​		<font color="red">2、什么是微服务雪崩现象？如何解决微服务雪崩问题？</font>

​			雪崩状态：微服务之间**相互调用**，因为调用链中的**一个服务故障**，引起**整个链路都无法访问**的情况

​			解决：**预防层面：使用限流，问题解决层面：可以用超时处理，舱壁模式也就是隔离，熔断和降级**我们是在控制台进行配置的

​		<font color="red">3、sentinel的限流模式有哪些？分别的运用场景是什么？</font>

​			**限流模式有直联，关联，链路，限流效果有快速失败，warm up，排队等待**

​		**直联**：统计当前的资源请求，触发阈值时对该资源进行限流

​		**关联**：统计当前资源相关的另一个资源，触发阈值时，对当前资源限流

​			**场景**：比如用户支付时需要修改订单状态，同时用户要查询订单，查询和修改操作会去抢数据库锁，产生竞争。业务需求是优先支付和更新订单业务，因此当修改订单业务触发阈值时，对查询订单业务限流

​		**链路**：统计从指定链路访问到本资源的请求，触发阈值时，对指定链路限流

​			**场景**：查询商品和创建订单业务，两者都需要查询商品，这个时候业务需求是优先满足创建订单，这时就可以对查询商品做限流

​		<font color="red">4、sentinel的限流效果有哪些？分别的运用场景是什么？</font>

​		**快速失败：**达到阈值后，新的请求会被立即拒绝并抛出FlowException异常。是默认的处理方式。

​		**warm up：**预热模式，对超出阈值的请求同样是拒绝并抛出异常。但这种模式阈值会动态变化，从一个较小值逐渐增加到最大阈值。

​				**场景**：预热启动 ，当一个服务刚刚启动时，一切资源未能初始化，如果直接将QPS跑到最大值，会导致宕机，这个时候就需要warm up      

​		**排队等待：**让所有的请求按照先后次序排队执行，两个请求的间隔不能小于指定时长

​				 **场景**：快事失败和 warm up在超出QPS阈值时都会直接抛出异常，而排队等待则会让所有请求进入一个队列中，按照阈值运行的时间间隔依次执行，后面的请求必须等待前面的执行完成

​		<font color="red">5、sentinel支持对热点参数进行限流吗？</font>

​			支持

​		<font color="red">6、实现微服务调用隔离有两种方式（信号量隔离和线程池隔离），区别是什么？sentinel是使用的哪种？</font>

​			**隔离方式：**信号量隔离和线程池隔离，sentinel默认采用的是信号量隔离

​		区别：

​		**信号量隔离**：**优点**：轻量级，无额外开销  **缺点**：不支持主动超时，不支持异步调用 

​		**线程池隔离**：**优点**：支持主动超时，异步调用  **缺点**：线程的额外开销大当然sentinel也可以实现线程隔离，就是开启舱壁模式

​		<font color="red">7、什么是熔断？熔断的原理是什么？什么时候会触发sentinel的熔断？断路器的三种状态是哪些？是怎样进行切换的？</font>

​		**什么是熔断**：拦截访问该服务的一切请求，当服务恢复时，断路器会放行访问该服务的请求

​		**原理：**由断路器统计服务的异常比例，异常数，慢请求比例，如果超出阈值就会熔断该服务断路器三种状态：

​		**closed：关闭状态**，断路器会放行所有请求，并开始统计异常比例，异常数，慢请求比例，**超过阈值则会切换到open状态**

​		**open：打开状态，**服务调用将会熔断，访问熔断服务的请求会被拒绝，快速失败，直接走降级逻辑，**open状态5秒后会进入half-open状态**

​		**half-open：半开状态**，**放行一次请求如果请求成功切换到closed状态，请求失败切换到open状态**

​		<font color="red">8、什么是降级？如何实现降级？</font>

​			降级：可以理解为，我访问这个服务失败了，但是又不能直接给用户显示出来，这个时候给一个别的画面给用户看，可以是404，也可以是请稍后

**实现降级：客户端定义降级方法，方式由两种**

​                  **1：FallBackClass**

​                  **2：FallBackFactoryClass（一般用这个好点，可以直接获取服务端抛出的异常）**

​		<font color="red">9、sentinel授权规则是用来干什么的？</font>

​			**对请求方**来源做**判断和控制**，有**黑白名单两种方式**，可以让**网关来访问该资源，禁止服务器直接访问**

​		<font color="red">10、sentinel的规则持久化方式有哪些？一般使用哪种？</font>	

​			**原始模式**：**Sentinel默认方式**，将规则保存到内存中，重启服务会丢失

​			pull模式：控制台将配置推送到远程控制中心，如Nocas

​			push模式

## 6、网关

​	<font color="red">1）、网关有什么作用？在你们项目中用网关来干嘛了？</font>

​			把网关当作防火墙，一切访问服务的连接都要经过网关，是所有微服务的入口

​			**网关的作用：**权限控制，路由和负载均衡，限流

​	<font color="red">2）、网关的核心技术点有哪些？</font>

​			路由，过滤工厂，断言工厂

​	<font color="red">3）、网关的路由是用来干嘛的？分为哪几种？</font>

​			路由就是把这个拦截到访问的网址后，校验这个网址后去访问我们微服务的真实配制的路径

​			种类分两种：静态路由，动态路由

​	<font color="red">4）、网关的过滤器是用来干嘛的？分为哪几种？</font>

​		过滤器可以对进入网关的请求微服务返回的响应做处理

​		分为三种：默认过滤器，局部过滤器，全局过滤器

​	<font color="red">5）、网关局部过滤器和全局过滤器的区别有哪些？</font>

​		**局部过滤器**由内置的三十一种局部过滤器工厂，可以针对某个路由配置，或针对全部路由的默认过滤器

​		**全局过滤器**需要自己通过代码实现，实现Filter方法，执行顺序要用过order接口或是注解，一般用来定义各个web服务的公共逻辑，如用户鉴权，日记记录等

​	<font color="red">6）、网关中局部过滤器、默认过滤器、全局过滤器的执行顺序是什么？</font>

​		先看order属性，order属性越小越先执行，如果一样执行顺序为默认，局部，全局

​	<font color="red">7）、加入网关后，访问一个链接，你们项目的执行流程是什么？</font>

​		geteway Client向geteway Server发送请求

​		请求会被HttpWebHandlerAdapter进行提取组装成网关上下文

​		将网关上下文传递到DispatcherHandler，它负责将请求发送给RoutePredicateHandlerMapping

​		RoutePredicateHandlerMapping负责路由查找，并根据路由断言判断路由路由是否可用

​		如果断言成功，由FilteringWebHandler创建过滤器链并调用

​		请求一次会经过preFilter—微服务—postFilter，最终返回响应

​	<font color="red">8）、定义全局过滤器需要实现哪几个接口？</font>

​		实现filter接口和order接口

## 7、分布式事务

​	<font color="red">1）、什么是本地事务？什么是分布式事务？</font>

​		**本地事务：**无需跨越多个服务或者数据源的单体事务，一般都是由spring控制

​		**分布式事务：**指一个业务跨越多个服务或数据源，每个事务叫分支事务，要保证所有分支事务，要么全成功，要么全失败

​	<font color="red">2）、什么是CAP定理？为什么必须保证P？为什么在保证P的前提下只能保证C或者A其中一个？</font>

​		CAP：P必须满足，C或A满足其中一个

​		C：数据一致性，任何时候，访问任何节点返回的数据都是一致的

​		A：服务可用性，任何时候，访问任何节点都要能够得到响应

​		P：分区容错性，因为网络故障或其他原因导致分布式系统中部分节点与其他节点失去连接，要形成独立分区，出现分区后整个系统也要持续对外提供服务

​	<font color="red">3）、什么是BASE理论？</font>

​		**Basically Avalible（基本可用）**：分布式系统出现故障时，允许损失部分可用性，保证核心可用

​		**Soft State（软状态）**：在一定时间内，允许出现中间状态，比如临时的不一致状态

​		**Evantually Consistent（最终一致性）**：虽然无法保证强一致，但在软状态结束后，最终达成数据一致

​	<font color="red">4）、seata解决分布式事务的三个角色以及分别的作用什么？</font>

​		**TC 事务协调者：**维护全局和分支事务的状态，协调全局事务提交或回滚

​		**TM 事务管理者：**定义全局事务范围，开始全局事务，提交或回滚

​		**RM 资源管理者：**管理分支事务处理的资源，与TC交谈注册分支事务和报告分支事务，并驱动分支事务提交或回订单是用不到这个全局锁的，他是不涉及到数据的脏写的，我说的这种情况才涉及到

​	<font color="red">5）、seata解决分布式事务的四种模式</font>

​		**TA：**强一致性分阶段事务模式，牺牲了一定的可用性，无业务入侵

​		**AT：**最终一致的分阶段事务模式，无业务入侵，也是Seate默认模式

​		**TCC：**最终一致的分阶段事务模式，有业务入侵

​		**SAGA：**长业务模式，有业务入侵

![0](https://note.youdao.com/yws/public/resource/05a9ab7d3dbc8584b065d13f768a2b6c/xmlnote/WEBRESOURCE1e4f9e2a20f65fcd53d35d80b0d76b29/9270)

​	<font color="red">6）、XA模式特点、原理以及应用场景？优缺点有哪些？</font>

​		**XA：**强一致性分阶段事务模式，牺牲了一定的可用性，无业务入侵

​		**原理：**

​		第一阶段：

​			1、TM开启全局事务，调用分支事务

​			2、TC接收开启全局事务请求

​			3、RM将分支事务注册到TC，执行本地SQL但不提交，将本地事务状态报告给TC

​		第二阶段：

​			1、TM等一阶段所有分支事务执行完，发起提交/回滚全局事务

​			2、TC接收全局事务提交/回滚请求，查询所有的分支事务状态，对RM发起提交/回滚命令

​			3、RM依赖数据库，提交/回滚当前的分支事务

​		优点：强一致性，无代码入侵，简单

​		缺点：强依赖于关系型数据库实现回滚，性能较差

​	<font color="red">7）、AT模式特点、原理以及应用场景？优缺点有哪些？有可能会出现什么问题？如何解决？</font>

​		AT：最终一致的分阶段事务模式，无业务入侵，也是Seate默认模式

​		原理：

- ​        第一阶段：
- ​                         TM开启全局事务，调用分支事务
- ​                         TC接收开启全局事务请求
- ​                         RM将分支事务注册到TC，执行本地SQL提交，执行前拍一个快照Undo-log，将本地事务状态报告给TC
- ​        第二阶段：
- ​                         TM等一阶段所有分支事务执行完，发起提交/回滚全局事务
- ​                         TC接收全局事务提交/回滚请求，查询所有的分支事务状态，对RM发起提交/回滚命令
- ​                         RM依赖于Undo-log快照数据，提交/回滚当前的分支事务

优点：一阶段可用直接提交事务，释放资源，性能较好。利用全局锁实现读写隔离，没有代码入侵

缺点：二阶段属于软状态，属于最终一直。框架的快早功能也会影响性能，但是比XA也好很多

可能出现的问题：脏写，当全局事务1提交修改的数据后，此时全局事务2又过来修改了这条数据 后续阶段二全局事务1需要利用快照进行回滚，将全局事务2的所有修改进行了覆盖

如何解决：seata内部提供了全局锁的概念（需要在seata server新增一张全局锁的表但是全局锁有可能导致死锁（内部通过限制获取全局锁的次数来解决：30次/10ms）

​	<font color="red">8）、重点：TCC模式特点、原理以及应用场景？优缺点有哪些？有可能会出现什么问题？什么是空回滚和业务悬挂，如何解决？</font>

​	<font color="red">9）、SAGA模式特点、原理以及应用场景？优缺点有哪些？	</font>

## 8、分布式ID生成方案

<font color="red">1）、UUID	</font>

​	算法核心思想是饥饿和机器网卡、当地时间、一个随机数来生成UUID

​	优点：本地生成，生成简单，性能好，没有高可用风险

​	缺点：长度过长，存储冗余，无序不可读，查询效率低

<font color="red">2）、数据库自增ID	</font>

​	优点：数据库生成的id绝对的有序，高可用实现方式简单

​	缺点：需要独立部署数据库实例，成本高，有性能瓶颈

<font color="red">3）、数据库批量生成ID	</font>

​	优点：避免了每次生成ID都需要访问数据库带来的压力，提高了性能

​	缺点：属于本地生成策略，存在单点故障，服务重启造成id不连续

<font color="red">4）、Redis生成ID	</font>

​	优点：不依赖数据库，灵活方便，且性能优于数据库，数字id天然排序，对分页或者是需要排序的结果很有帮助

​	缺点：如果没有redis需要引入新的组件

<font color="red">5）、Twitter的snowflflake算法（雪花算法）	</font>

snowflake是Twitter开源的分布式ID生成算法，结果是一个long型的ID。其核心思想是：使用41bit作为毫秒数，10bit作为机器的ID（5个bit是数据中心，5个bit的机器ID），12bit作为毫秒内的流水号（意味着每个节点在每毫秒可以产生 4096 个 ID），最后还有一个符号位，永远是0。

​	1、最高位是符号位，始终为0，不可用。

​	2、41位的时间序列，精确到毫秒级，41位的长度可以使用69年。时间位还有一个很重要的作用是可以根据时间进行排序。

​	3、10位的机器标识，10位的长度最多支持部署1024个节点。

​	4、12位的计数序列号，序列号即一系列的自增id，可以支持同一节点同一毫秒生成多个ID序号，12位的计数序列号支持每个节点每毫秒产生4096个ID序号。

<font color="red">6）、百度的UidGenerator	</font>

UidGenerator 是 Java 实现的，基于 [Snowflake](https://www.oschina.net/p/twitter-snowflake) 算法的唯一 ID 生成器。

UidGenerator 以组件形式工作在应用项目中，支持自定义 WorkerID 位数和初始化策略，从而适用于 Docker 等虚拟化环境下实例自动重启、漂移等场景。

在实现上，UidGenerator 通过借用未来时间来解决 sequence 天然存在的并发限制；采用 RingBuffer 来缓存已生成的 UID，并行化 UID 的生产和消费，同时对 CacheLine 补齐，避免了由 RingBuffer 带来的硬件级「伪共享」问题。最终单机 QPS 可达 600 万。

<font color="red">7）、美团的Leaf	</font>

## 9、微服务接口响应慢

1、**异步处理：**尽量使用异步处理方式，避免同步阻塞等待，从而提高系统的并发能力和响应速度。例如使用消息队列，异步调用等

2、**负载均衡：**使用负载均衡技术，将请求分散到多个服务实例中，避免单一服务负载过高，导致响应变慢。常见的负载均衡技术有轮询、随机、哈希等。

3、**数据库优化：**数据库是服务性能的瓶颈之一，可以优化数据库连接、索引等，从而提高数据库访问速度。例如使用缓存、分库分表等技术。

4、**延迟降级：**可以在服务调用链路中设置延迟降级策略，当服务响应时间超过一定阈值时，采取降级措施，例如返回缓存数据或默认值，从而提高服务的可用性。

5、**缓存：**使用缓存技术，将一些常用的数据缓存到内存中，减少服务对数据库的访问次数，提高接口响应速度。例如使用Redis、Memcached等技术。

6、**加强日志监控：**可以在系统中加入监控和日志记录，及时发现和排查慢接口问题。

7、**采用熔断机制：**可以采用熔断机制，当某个服务出现异常或响应时间超时时，及时断开请求，避免影响整个系统的性能和可用性。



# 九、场景问题

<font color="red">1.如何去设计一个高并发的系统？</font>

​	1、系统拆分：可以将一个系统才分为多个子系统，让每个系统连自己的数据库，多个数据库也可以抗下高并发。

​	2、缓存：大部分高并发场景都是读多写少，完全可以在数据库跟缓存中都写一份，然后读的时候大量走缓存就行了（要考虑的问题是哪些是热点数据，哪些数据需要放进缓存，数据一致性问题，缓存雪崩、击穿、穿透问题等）

​	3、MQ:既然是高并发，高并发写的问题肯定是避免不了的，MQ的作用就是异步解耦、削峰填谷，可以把大量请求放到MQ里面，排队慢慢消费（但要考虑数据库能承载的范围，数据库的链接上限）

​	4、分库分表：如果数据库还是肯不了压力，可以考虑分库分表，一个库分为多个库，一张表分为多张表提高性能（需要考虑按那种维度去分库了，分表也是水平还是垂直）

​	5、读写分离：因为对于大部分数据库来说都是读多写少的，没必要所有请求没必要所有请求都到一个数据库上面，可以选择主从架构，主库写，从库读。读的请求多的话可以添加从库

​	6、ElasticSearch:es是分布式的，可以随时扩容，天生就支持高并发。想一些简单的查询、统计类的操作，或者是全文检索都可以使用es来完成。

<font color="red">2.为什么大厂规定不能使用Excutors去创建线程池？</font>

```java
ExecutorService executorService = Executors.newFixedThreadPool(1);
//他是会生成一个线程数量固定的一个线程池，但是使用的是容量没有上限的队列，如果线程处理速度比较慢就会造成任务积压，达到一定量就会OOM
ExecutorService executorService1 = Executors.newSingleThreadExecutor();
//同意的，这个是创建只有一个线程的线程池，但使用的还是无界队列，任务一多，处理不过来还是可能会造成OOM
ExecutorService executorService2 = Executors.newCachedThreadPool();
//这个是创建一个核心线程数为0,但是最大线程数为Integer.MAX_VALUE（Intefer的最大值2的32次方-1） 使用的是SynchronousQueue是不会存储任务的。任务一来就会创建线程，线程数量一多从而导致内存不足，导致OOM

ScheduledExecutorService scheduledExecutorService = Executors.newScheduledThreadPool(1);

ScheduledExecutorService scheduledExecutorService1 = Executors.newSingleThreadScheduledExecutor();
```



# 九、Docker

##### <font color="red">0、Linux</font>

查看日志

```
tail:
-n 是显示行号；相当于nl命令；例子如下：
tail -100f test.log 实时监控100行日志
tail -n 10 test.log 查询日志尾部最后10行的日志;
tail -n +10 test.log 查询10行之后的所有日志;

head:
跟tail是相反的，tail是看后多少行日志；例子如下：
head -n 10 test.log 查询日志文件中的头10行日志;
head -n -10 test.log 查询日志文件除了最后10行的其他所有日志;

cat：
tac是倒序查看，是cat单词反写；例子如下：
cat -n test.log |grep "debug" 查询关键字的日志

使用more和less命令
```

查看进程

```
查看java进程：ps -ef|grep java
查看java进程名占用进程的进程id：pgrep java
查看指定进程id的运行目录：pwdx 54096

2、杀进程
    linux:  kill -9 进程ID
    windows： tastkill /PID 进程ID /F
    
    1、查看端口占用
    netstat -tunlp | grep 端口号
    lsof -i:端口号  （需要root权限执行）【安装lsof：yum -y install lsof.*】
```



##### 	<font color="red">1、什么是Docker？优点是什么？有哪些核心概念？</font>

​		微服务虽然具备各种各样的优势，但服务的拆分通用给部署带来了很大的麻烦。所以出现了Docker解决微服务部署问题。

##### 	<font color="red">2、镜像操作命令有哪些？</font>

```
    0）、搜索：docker search 镜像名称
    1）、拉取：docker pull
    2）、推送：docker push
    3）、查看：docker images
    4）、查看所有镜像ID：docker images -q
    5）、删除：docker rmi 镜像名称
    6）、删除所有：docker rmi `docker images -q`
    7）、制作镜像：docker build . 
    8）、导出镜像：docker save -o 镜像名称.tar 镜像名称
    9）、加载镜像：docker load -i 镜像名称.tar
    10）、容器转为镜像：docker commit 容器名称 镜像名称
```

##### 	<font color="red">3、容器操作命令有哪些？</font>

```
 0）、开启服务    systemctl start docker.service
    1）、查看所有：docker ps -a
    2）、查看正在运行：docker ps 
    3）、删除：docker rm 容器名称
    4）、强制删除：docker rm -f 容器名称
    5）、创建容器：docker create -d --name 容器名称 -p 宿主机端口：容器内端口 镜像名称
    6）、创建并运行容器：docker run -d --name 容器名称 -p 宿主机端口：容器内端口 镜像名称
    7）、启动容器：docker start 容器名称
    8）、停止容器：docker stop 容器名称
    9）、重启容器：docker restart 容器名称
    10）、暂停容器：docker pause 容器名称
    12）、恢复容器：docker unpause 容器名称
    13）、进入容器：docker exec -it 容器名称 /bin/bash
    14）、查看容器信息：docker inspect 容器名称或者容器id
```

##### 	<font color="red">4、数据卷操作命令有哪些？</font>

​		创建数据卷、查看单个数据卷详情、查看数据卷列表、删除数据卷、删除未使用的数据卷、创建容器时挂载数据卷

```
 1）、创建数据卷：docker volume create 数据卷名称  （位于/var/lib/docker/volume目录）
    2）、查看单个数据卷详情：docker volume inspect 数据卷名称
    3）、查看数据卷列表：docker volume ls
    4）、删除数据卷：docker volume rm 数据卷名称
    5）、删除未使用的数据卷：docker volume prune
    6）、创建容器时挂载数据卷
    	1）、挂载数据卷（会自动创建数据卷）：docker run -v 数据卷名称：容器内目录路径
    	2）、挂载指定目录（要自己创建）：docker run -v 目录绝对路径：容器内目录路径
```

##### 	<font color="red">5、docker如何自定义镜像？docker file的语法是什么样的？</font>



##### 	<font color="red">6、docker compose是干嘛的?语法是什么样的？</font>


​	Compose文件是一个文本文件，通过指令定义集群中的每个容器如何运行。可以理解为一个运行脚本。
​	

# 十、ElasticSearch

##### 	<font color="red">1、什么是ES？由什么语言编写？和Lunce的关系？什么是ELK？</font>

​		1）、是一款分布式、高性能、高扩展，支持海量数据分析、搜索、计算的搜索引擎

​		2）、基于java语言编写，发起的请求是基于json风格的符合RestFull风格的DSL语句

​		3）、前身-Lucene诞生于1999年，2004年变为了compass，2010年重构成了现在的ES

​		4）、ELK：是一个围绕ElasticSearch的技术栈，包含：ElasticSearch、Logstatsh、Kibana，最新版本7.16.3

##### 	<font color="red">2、ES的核心概念有哪些？什么是索引？什么是文档？文档格式是什么？什么是映射？什么是DSL？</font>

​		1）、索引-index：同一类型文档的集合，相当于mysql的表

​		2）、映射-mapping：对索引结构的约束，相当于mysql的schema

​		3）、文档-document：json格式的数据，相当于mysql的row(行)

​		4）、字段-field：一个个的字段，相当于mysql的列

​		5）、DSL语句：json风格的符合restful风格的请求语句，相当于mysql的sql语句

##### 	<font color="red">3、什么是倒排索引？倒排索引建立过程？</font>

​		倒排索引，是通过分词策略，形成了词和文章的映射关系表，

​		1、在文档【增删改】的时候对文档进行【合理化的分词】，形成一个不重复的词条列表，其中每一个词条对应一个文档id集合

​		2、形成一颗根据词条查询id的B+tree

​		3、形成一颗根据id查询文档的B+tree

​		将来搜索时先根据用户输入的条件进行【合理化的分词】，再根据词条找id，最后根据id找到相应的文档（涉及到两次Btree
查询）

##### 	<font color="red">4、ES有哪些数据类型？keyword和text有什么区别？</font>

​		**数值**：long、integer、short、byte、double、float、

​		**布尔**：boolean

​		**日期**：date

​		**对象**：object

​		**字符串**：text（可分词的文本）、keyword（精确值，例如：品牌、国家、ip地址）

##### 	<font color="red">5、重要：说说用户输入框输入查询条件 进行ES搜索的底层原理过程</font>

​		1）用户输入条件`"华为手机"`进行搜索。

​		2）对用户输入内容**分词**，得到词条：`华为`、`手机`。

​		3）拿着词条在倒排索引中查找，可以得到包含词条的文档id：1、2、3。

​		4）拿着文档id到正向索引中查找具体文档。

##### 	<font color="red">6、ES分词器适合在什么字段上使用？分词器在ES中的使用场景有哪些？（建立倒排索引时对文档分词和用户搜索时对搜索条件分词）</font>

​		适合在需要查询的字段上

##### 	<font color="red">7、你们分词器用的哪种？为什么要自定义拼音分词器？为什么搜索时不能用拼音分词器？</font>

​		ik分词器，Pinyin分词器，自定义分词器

​		拼音分词器对我们每一个汉字都解析出对应的中文，但是这个并不是我们所需要的结果，我们需要的结 果基于ik 分词器的基础上的拼音，比如： 长隆大马戏可以分词出马戏， 那么就应该有对应的拼音， maxi。 如果我们需要实现该效果我们则需要自定义分词器。

​		搜索时用拼音分词器，会出现同音跟谐音比如：狮子，虱子，并不是我们想要的结果。

##### 	<font color="red">8、ES有哪些查询类型，分别用在什么场景？如何实现复合查询？要给指定的数据进行加分如何实现？</font>



##### 	<font color="red">9、ES能对搜索结果进行哪些处理？如何实现高亮？</font>



##### 	<font color="red">10、ES有哪些聚合查询？</font>

​	**1、分桶聚合(Bucket aggregations)**

​		分桶聚合类似与关系型数据库的Group By查询,按照指定的条件,进行分组统计.

​	**2、指标聚合(Metrics aggregations)**

​		指标聚合主要是计算指标的Avg(平均值)、Max(最大值)、Min(最小值)、Sum(求和)、Cardinality(去重)、ValueCount(记数)、Stats(统计聚合)、Top Hits(聚合)等.

​	**3、管道聚合(Pipeline aggregations)**

​		管道聚合主要用于对聚和结果的二次聚合,举个例子,这里需要计算某个商城中的各个品牌手机价格平均值中最小的手机品牌.这里第一步需要计算各个手机品牌价格的平均值,接着计算平均值中的最小值,这里就需要用到管道聚合.

##### 	<font color="red">11、ES如何实现自动补全查询</font>

##### 	<font color="red">12、如何自定义分词器？</font>

##### 	<font color="red">13、如何实现es与mysql的数据同步？</font>

​	一共有三种方案：同步调用、异步通知、监听binlog

​	我们使用的是异步，通过MQ发消息进行数据同步

##### 	<font color="red">14、es集群节点有哪些类型？分别的职责是什么？</font>

​	1、**主节点（Master）:** master节点在每个集群中有且只有一个。Master节点应该只承担较为轻量级的任务，比如：创建删除索引，分片均衡等。

​	2、**候选节点（Master-eligible node）:** 和主节点的配置相同，在选举时可以被选举为主节点。

​	3、**数据节点（Data node）：**这样的节点主要负责数据存储和一些查询服务。

​	4、**协调节点（coordinating）：** 每一个节点都隐式的是一个协调节点，协调节点既不当候选节点，也不作为数据节点，仅负责负载均衡，进行投票。

##### 	<font color="red">15、什么是es脑裂问题？</font>

​	假设有三个节点组成的集群，主节点与其他节点失联，这时另外两个节点会认为主节点宕机了，会推举新的主节点出来，当新的主节点诞生后，此时之前的主节点又恢复过来。这样就会让失联之前的主节点和推举的主节点自成两个集群，出现数据差异

​	**解决：**要求选票超过（节点数量+1）/2，因此最好节点的数量是奇数，在ES7.0以后就默认该配置了，一般不会出现

​	

# 十一、压测、高并发性能优化

​	1、jemiter压测工具使用



2	2、多级缓存（nginx共享字典、redis缓存、tomcat进程缓存）
​	3、数据库主从读写分离（mycat）
​	4、发布：
​		开发环境、测试环境用的shell脚本自动发布（包括从git上拉取代码、打包编译、启动）
​		预上线、线上环境用的jenkins持续集成	
​	5、提交代码之前需要做什么？git pull
​	



# 十二、Maen相关面试题

##### <font color="red">1、Maen依赖原则</font>

​		a、**最短路径原则**：如果项目中就出现了两个版本的依赖，这时maven会采用最短路径原则，选择V2版本的D，因为V1版本的D是由A包间接依赖的，整个依赖路径长度为3，而V2版本的D是由F包间接依赖的，整个依赖路径长度为2。

​		b、**优先声明原则：**如果两个jar包版本路径深度相同，则使用优先声明的版本

​		c、多次直引不同版本的jar时，使用最后声明的版本（本人实测）

##### <font color="red">2、如何解决依赖冲突？</font>

<div id="content_views" class="htmledit_views">
                    <p>1.java常用的包依赖异常有：</p> 
<p>1）<strong>AbstractMethodError</strong></p> 
<p><strong>2）NoClassDefFoundError</strong></p> 
<p><strong>3）ClassNotFoundException</strong></p> 
<p><strong>4）LinkageError</strong></p> 
<p>Maven会根据pom文件中的groupId、artifactId、version来判断jar是否冲突</p> 
<p>如果出现了同名不同版本的jar包,Maven的处理原则是 离你项目更近的jar包会被选中,其他的淘汰&nbsp;</p> 
<p>2.处理jar冲突</p> 
<p>1）下载Idea插件 Maven Helper</p> 
<p>File–&gt;setting—&gt;Plugins—&gt;在搜索框中填写Maven Helper然后搜索，单击Install按钮进行安装，装完重启IDE。</p> 
<p><img alt="" height="703" src="https://img-blog.csdnimg.cn/da5a8a61a185449296ba5162998b8b42.png" width="983"></p> 
<p>当Maven Helper 插件安装成功后，打开项目中的pom文件，下面就会多出一个视图Dependency Analyzer：</p> 
<p><img alt="" height="240" src="https://img-blog.csdnimg.cn/1d8848272caf4e68a155b97495b7bc7f.png" width="612"></p> 
<p>切换到此试图即可进行相应操作：<br><strong>Conflicts（查看冲突）<br> All Dependencies as List（列表形式查看所有依赖）<br> All Dependencies as Tree（树形式查看所有依赖）</strong></p> 
<p><img alt="" height="696" src="https://img-blog.csdnimg.cn/350e1c7e15b646529181029babb9a4b8.png" width="1093"></p> 
<p>2、解决冲突：</p> 
<p>方法1：更换兼容版本<br> 方法2：右键单击红色区域，弹出菜单选择Exclude命令，对冲突进行排除。</p> 
<p><img alt="" height="553" src="https://img-blog.csdnimg.cn/e2c8469c96ad4bc0828963bc5392f72b.png" width="1200"></p> 
                </div>
<font color="red">3、如何排除依赖</font>

```pom
<exclusions>
	<exclusion>
		<groupId>com.xxx.xxx</groupId>
		<artifactId>xxx1<artifactId>
	</exclusion>
	
	<exclusion>
		<groupId>com.xxx.xxx</groupId>
		<artifactId>xxx2<artifactId>
	</exclusion>
	
</exclusions>
```



# 十三、设计模式

1、什么是设计模式？

​	简单说就是针对某种场景下，解决某类问题的通用方案；

2、设计模式分哪几类？

​	创建型模式：对象实例化的模式，创建型模式用于解耦对象的实例化过程；共有一下几种：**工厂方法模式**、**抽象工厂模式**、**单例模式**、**建造者模式**、**原型模式**。

​	结构型模式：把类或对象结合在一起形成一个更加强大的结构；共有一下几种：**适配器模式**、**装饰器模式**、**代理模式**、**外观模式**、**桥接模式**、**组合模式**、**享元模式**。

​	行为型模式：类和对象如何交互，及划分职责和算法；共有一下几种：**策略模式**、**模板方法模式**、**观察者模式**、**迭代子模式**、**责任链模式**、**命令模式**、**备忘录模式**、**状态模式**、**访问者模式**、**中介者模式**、**解释器模式。**

3、常用的设计模式？

​	**单例模式：**Spring容器里的Bean默认都是单例模式，线程池

​	**工厂模式：**像SqlSessionFactory、BeanFactory，threadFactory等都是工厂模式

​	**装饰模式：**动态地给一个对象添加一些额外的职责。就增加功能来说，装饰器模式相比生成子类更为灵活。

​	**策略模式：**功能：具体算法从具体业务处理中独立、多个if-else出现考虑使用策略模式

​	**代理模式：**Spring的AOP就是利用的代理模式，分JDK 动态代理和 CGLIB 动态代理：

​			(1)JDK 动态代理只提供接口代理，不支持类代理，核心 InvocationHandler 接口和 Proxy 类，InvocationHandler 通过 invoke()方法反射来调用目标类中的代码，动态地将 横切逻辑和业务编织在一起，Proxy 利用 InvocationHandler 动态创建一个符合某一接口 的的实例, 生成目标类的代理对象。 

​			(2) 如果代理类没有实现 InvocationHandler 接口，那么 Spring AOP 会选择使用 CGLIB 来动态代理目标类。CGLIB（Code Generation Library），是一个代码生成的类库， 可以在运行时动态的生成指定类的一个子类对象，并覆盖其中特定方法并添加增强代码，从 而实现 AOP。CGLIB 是通过继承的方式做的动态代理，因此如果某个类被标记为 final， 那么它是无法使用 CGLIB 做动态代理的





![image-20221014091657115](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20221014091657115.png)







