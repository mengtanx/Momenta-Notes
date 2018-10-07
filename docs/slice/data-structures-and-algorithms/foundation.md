# 基础篇

## 05 | 数组：为什么大多数编程语言中的数组要从 0 开始编号？

![数组](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181004114134.png)

在大部分编程语言中，数组都是从 0 开始编号的。但你出否想过，**为什么数组要从 0 开始编号，而不是从 1 开始呢？**从 1 开始不是更符合人类的思维习惯吗？

### 如何实现随机访问？

什么是数组？**数组 Array 是一种线性表数据结构。它用一组连续的内存空间，来存储一组具有相同类型的数据。**

![线性表](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181004114452.png)
![非线性表](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181004114625.png)

* 线性表 Linear List
    * 线性表就是数据排成像一条线一样的结构。每个线性表上的数据最多只有前和后两个方向。
    * 除数组外，链表、队列和栈等也是线性表结构。
    * 与其相对的概念是非线性表，如二叉树、堆、图等。非线性表中，数据之间并不是简单的前后关系。
* 连续的内存空间和相同类型的数据
    * 由于这两个限制，数组有了一个「杀手锏」般的特性：随机访问。
    * 同时，也让数组的很多操作变得非常低效，如在数组中删除、插入一个数据
    * 数组通过寻址公式计算数组中某个元素存储的内存地址即可实现随机访问数组中某个元素。
    * 纠正一个「错误」：链表与数组的区别，链表适合插入、删除，时间复杂度为 O(1)；数组适合查找，查找时间复杂度为 O(1)。更准确的表述为，数组支持随机访问，根据下标随机访问的时间复杂度为 O(1)。

### 低效的「插入」和「删除」

数组为了保持内存数据的连续性，会导致插入、删除这两个操作都比较低效。

* 插入操作：如果数组中的数据是有序的，可以将插入新元素的时间复杂度降为 O(1)。
* 删除操作：和插入类似，删除操作的最好情况时间复杂度为 O(1)，最坏情况时间复杂度为 O(n)，平均情况时间复杂度也为 O(n)。

在某些特殊场景下，我们并不一定非得追求数组中数据的连续性。我们可以将多次删除操作集中在一起执行，以提高删除的效率。每次的删除操作并不是真正地搬移数据，只是记录数据已经删除。当数组没有更多空间存储数据时，再触发执行一次真正的删除操作，这样就大大减少了删除操作导致的数据搬移。

数据结构与算法的魅力就在于，**很多时候我们并不是要去死记硬背某个数据结构或者算法，而是要学习它背后的思想和处理技巧，这些东西才是最有价值的。**

### 警惕数组的访问越界问题

```c
int main(int argc, char* argv[]){
    int i = 0;
    int arr[3] = {0};
    for (; i<=3; i++) {
        arr[i] = 0;
        printf("hello world\n");
    }
    return 0;
}
```

由于代码书写错误，导致 for 循环的结束条件错写为了 i<=3 而非 i<3，所以当 i=3 时，数组 a[3] 访问越界。而在 C 语言中，只要不是访问受限的内存，所有的内存空间都是可以自由访问的。根据数组寻址公式，a[3] 也会被定位到某块不属于数组的内存地址上，而这个地址正好是存储变量 i 的内存地址，那么 a[3]=0 就相当于 i=0，所以就会导致代码无限循环。

数组越界在 C 语言中是一种未决行为，并没有规定数组访问越界时应该如何处理。因为，访问数组的本质就是访问一段连续内存，只要数组通过偏移计算得到的内存地址是可用的，那么程序就可能不会报任何错误。

### 容器能否完全替代数组

针对数组类型，很多语言提供了容器类，如 Java 中的 ArrayList、C++ STL 中的 vector。**在项目开发中，什么时候适合用数组，什么时候适合用容器呢？**

以 Java 语言来举例，ArrayList 最大的优势就是**可以将很多数组操作的细节封装起来**。如数组插入、删除操作时需要搬移其他数据等。它的另一个优势就是**支持动态扩容**。ArrayList 底层已经实现了扩容逻辑，每当存储空间不够时，它都会将空间自动扩容为 1.5 倍大小。因为扩容曹禺设计内存申请和数据搬移，是比较耗时的。所以如果事先能确定需要存储的数据大小，最好**在创建 ArrayList 的时候实现指定数据大小。

有些时候，用数组会更合适，有以下几点经验总结：

1. Java ArrayList 无法存储基本类型，比如 int、long，需要封装为 Integer、Long 类，而 Autoboxing、Unboxing 则有一定的性能消耗，所以如果特别关注性能，或者希望使用基本类型，就可以选用数组。
2. 如果数据大小事先已知，并且对数据的操作非常简单，用不到 ArrayList 提供的大部分方法，也可以直接使用数组。
3. **个人喜好**：当要表示多维数组时，用数组往往会更加直观。如 Object[][] array; 而用容器则定义为 ArrayList<ArrayList>array。
4. 使用总结
    * 对于业务开发，直接使用容器就足够了，省时省力，对系统整体的性能影响非常小。
    * 如果做一些非常底层的开发，如开发网络框架，性能的优化需要做到极致，这时数组就会优于容器，成为首选。

### 解答开篇

从数组存储的内存模型上来看，「下标」最确切的定义应该是偏移量（）offerset。

数组时非常基础的数据结构，通过下标随机访问数组元素优势非常基础的编程操作，效率优化就要尽可能做到极致。所以为了减少一次剪发操作，数组选择了从 0 开始编号， 而不是从 1 开始。

数组起始编号为 0 最主要的原因可能是历史原因。

### 内容小结

* 数组用一块连续的内存空间，来存储相同类型的一组数据。
* 数组最大的特点是支持随机访问，但插入、删除操作也因此变得比较低效，平均情况时间复杂度为 O(n)。
* 在平时的业务开发中，我们可以直接使用编程语言提供的容器类，但是，如果是特别底层的开发，直接使用数组可能会更合适。

### 课后思考

1. 如果你理解并熟悉 JVM，可以回顾下你理解的标记清除垃圾回收算法。
2. 思考并类比一下，二维数组的内存寻址公式是怎样的呢？

## 06 | 链表（上）：如何实现 LRU 缓存淘汰算法？

首先来讨论一个经典的链表应用场景，那就是 LRU 缓存淘汰算法。缓存是一种提高数据读取性能的技术，在硬件设计、软件开发中都有着非常广泛的应用，比如常见的 CPU 缓存、数据库缓存、浏览器缓存等。

缓存的大小有限，当缓存被用满时，哪些数据应该被清理出去，哪些数据应该被保留？这就需要缓存淘汰策略来决定。常见的策略有三种：先进先出策略 FIFO（First In, First Out）、最少使用策略 LFU（Least Frequently Used）、最近最少使用策略 LRU（Least Recently Used）。

### 五花八门的链表结构

链表和数组的区别：从底层的存储结构上来看，数组需要一块**连续的内存空间**来存储，堆内存的要求比较高；链表并不需要连续的内存空间，它通过「指针」将一组**零散的内存块**串联起来使用。

![内存分布](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181005084647.png)

链表结构五花八门，三种常见的链表结构是：单链表、双向链表和循环链表。链表通过指针将一组零散的内存块串联在一起，我们把内存块称为链表的「结点」。为了将所有的结点串起来，每个链表的结点除了存储数据之外，还需要记录链上的下一个结点的地址。我们把这个记录结点地址的指针叫作**后继指针 next**。

* 单链表

单链表中有两个结点是比较特殊的，分别是第一个结点和最后一个结点。习惯性把第一个结点叫作**头结点**，把最后一个结点叫作**尾结点**。其中，头结点用来记录链表的基地址，有了它，我们就可以遍历得到整条链表。而尾结点特殊的地方是：指针不是指向下一个结点，而是指向一个**空地址 NULL**，表示这是链表上最后一个结点。

![单链表](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181005092749.png)

链表中插入或者删除一个数据，我们并不需要为了保持内存的连续性而搬移结点，因为链表的存储空间本身就不是连续的。所以，在链表中插入和删除一个数据非常快速的。针对链表的插入和删除操作，我们只需要考虑相邻结点的指针改变，所以对应的**时间复杂度是 O(1)**。

![链表的插入和删除](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181005085929.png)

但是，链表要想随机访问第 k 个元素，就没有数组那么高效了。因为链表中的数据并非连续存储的，需要根据指针一个结点一个结点地依次遍历，直到找到相应的结点。因此，**链表随机访问的时间复杂度是 O(n)**。

* 循环链表和双向链表

循环链表是一种特殊的单链表。它跟单链表唯一的区别就在尾结点。单链表的尾结点指向空地址，表示这就是最后的结点了。而循环链表的尾结点指针是指向链表的头结点。

![循环链表](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181005090347.png)

循环链表的优点是从链尾到链头比较方便。当要处理的数据具有环形结构特点时，就特别适合采用循环链表。比如[著名的约瑟夫问题](https://zh.wikipedia.org/wiki/%E7%BA%A6%E7%91%9F%E5%A4%AB%E6%96%AF%E9%97%AE%E9%A2%98)。

* 双向链表

在实际的软件开发中，更加常用的链表结构是：双向链表。单向链表只有一个方向，结点只有一个后继指针 next 指向后面的结点。而双向链表，支持两个方向，每个结点不止有一个后继指针 next 指向后面的结点，还有一个前驱指针 prev 指向前面的结点。

![双向链表](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181005090401.png)

双向链表需要额外的两个空间来存储后继节点和前驱结点的地址。所以，存储同样多的数据，双向链表要比单向链表占用更多的内存空间。双向链表的两个指针虽然比较浪费存储空间，但可以支持双向遍历，从而带来了双向链表操作的灵活性。思考一下，双向链表适合解决哪种问题呢？

从结构上看，双向链表可以支持 O(1) 时间复杂度的情况下找到前驱结点，从而使得双向链表在某些情况下的插入、删除等操作都要比单链表简单、高效。

* 删除操作：在实际软件开发中，从链表中删除一个数据无外乎两种情况：
    * 删除结点中「值等于某个给定值」的结点；
    * 删除给定指针指向的结点

对于第一种情况，不管是单向链表还是双向链表，为了查找到值等于给定值的结点，都需要从头结点开始一个一个依次遍历对比，直到找到值等于给定值的结点，然后再通过指针操作将其删除。**尽管单纯的删除操作时间复杂度是 O(1)，但遍历查找的时间是主要的耗时点，对应的时间复杂度为 O(n)。根据时间复杂度分析的加法法则，删除值等于给定值的结点对应的链表操作的总时间复杂度为 O(n)。

对于第二种情况，我们已经找到了要删除的结点，但是删除某个结点 q 需要知道其前驱结点，而单向链表并不支持直接获取前驱结点，所以还是要从头结点开始遍历链表，而对于双向链表中的结点已经保存了前驱结点的指针，可以直接在 O(1)
时间复杂度内就获取到前驱结点。

* 插入操作：同样地，我们在链表的某个指定结点前插入一个结点，双向链表比单链表有很大的优势。双向链表可以在 O(1) 时间复杂度内搞定，而单向链表需要在 O(n) 时间复杂度内搞定。

此外，对于一个有序链表，双向链表的按值查询的效率也要比单链表高一些。因为，我们可以及时上次查找的位置 p，每次查询时，根据要查找的值与 p 的大小关系，决定是往前还是往后查找，所以平均只需要查找一半的数据。

因此，在实际的软件开发中，双向链表尽管比较费内存，但还是比单链表的应用更加广泛的原因。如果你深入研究 Java 语言中的 LinkedHashMap 的实现原理，就会发现其中就用到了双向链表这种数据结构。

实际上，我们需要掌握一个更加重要的知识点：**空间换时间**的设计思想。当内存空间充足时，为了追求代码的执行速度，我们可以选择空间复杂度相对较高、但时间复杂度相对很低的算法或数据结构。相反，如果内存比较紧缺，比如代码跑在手机或者单片机上时，就要反过来用时间换空间的设计思路。缓存实际上就是利用空间换时间的设计思想。总结来说，对于执行较慢的程序，可以通过消耗更多的内存（空间换时间）来进行优化；而消耗过多内存的程序，可以通过消耗更多的时间（时间换空间）来降低内存的消耗。

* 双向循环链表

![双向循环链表](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181005100342.png)

### 链表 VS 数组性能大比拼

| 时间复杂度 | 数组 | 链表 |
| --- | --- | --- |
| 插入、删除 | O(n) | O(1) |
| 随机访问 | O(1) | O(n) |

对于数组和链表的对比，并不能局限于时间复杂度。在实际软件开发中，不能仅仅利用复杂度分析就决定使用哪个数据结构来存储数据。

* 数组简单易用，在实现上使用的是连续的内存空间，可以借助 CPU 的缓存机制，预读数组中的数据，所以访问效率更高。
* 链表在内存中并不是连续存储的，所以对 CPU 缓存不友好，没办法有效预读。
* 数组的缺点是大小固定，声明后就要占用整块连续内存空间。若声明的数组过大的，系统可能没有足够的连续内存空间分配导致内存不足（OOM）。
* 若声明的数组过小，则可能出现不够用的情况，这是需要再申请一个更大的内存空间，然后把原数组拷贝进去，非常费时。链表本身没有大小的限制，天然地支持动态扩容，这是与数组最大的区别。
* 此外，如果对代码内存的使用非常苛刻，那数组更加适合你。因为链表中的每个结点都需要消耗额外的存储空间去存储一份指向下一个结点的指针，所以内存消耗会翻倍。并且对链表进行频繁的插入、删除操作，还会导致频繁的内存申请和释放，容易造成内存碎片，对 Java 语言来说就有可能导致频繁的 GC。

### 解答开篇

如何基于链表实现 LRU 缓存淘汰算法？

思路如下：我们维护一个有序单链表，越靠近链表尾部的结点是越早之前访问的。当有一个新的数据被访问时，我们从链表头开始顺序遍历链表。

1. 如果此数据之前已经被缓存在链表中了，我们遍历得到这个数据对应的结点，并将原来的位置删除，然后再插入到链表的头部。
2. 如果此数据没有在缓存链表中，又可以分为两种情况：
    * 如果此时缓存未满，则将此结点直接插入到链表的头部；
    * 如果此时缓存已满，则将链表尾结点删除，将新的数据结点插入链表的头部。

基于链表实现缓存的思路，缓存访问的时间复杂度为 O(n)。实际上，我们可以引入散列表（Hash Table）来记录每个数据的位置，将缓存访问的时间复杂度降到 O(1)。此外，也可以用数组来实现 LRU 缓存淘汰策略，思考一下该如何利用数组实现呢？

### 内容小结

* 链表也是一种非常基础和常用的数据结构。
* 常用的链表包括单链表、双向链表、循环链表、双向循环链表。
* 链表更适合插入、删除操作频繁的场景，其查询的时间复杂度较高。
* 在具体的软件开发中，需要综合对比数组和链表的各种性能来选择。

### 课后思考

* 原始问题：如何判断一个字符串是否是回文字符串的问题？
* 衍生问题：如果字符串时通过单链表存储的，那该如何判断是一个回文串呢？分享一下你的解决思路及其时间和空间复杂度。

## 07 | 链表（下）：如何轻松写出正确的链表代码？

想要写好链表代码并不是容易的事儿，尤其是那些复杂的链表操作，比如链表翻转、有序链表合并等，写的时候非常容易出错，能把「链表翻转」这几行代码写对的人不足 10%。只要愿意投入时间，大多数人是可以写出正确的链表代码的。**比如，花上一个周末或者一整天的时间，就去写链表翻转一个代码，多谢几遍，一直练到毫不费力地写出 Bug Free 的代码。**

自己有决心并且付出精力是成功的先决条件。此外，我们也需要掌握一些方法和技巧，具体如下：

### 技巧一：理解指针或引用的含义

要想写对链表代码，首先要理解好指针。

我们知道，有些语言有「指针」的概念，如 C 语言；有些语言没有指针，取而代之的是引用，如 Java、Python。不管是指针还是引用，实际上，它们的意思都是一样的，都是存储所指对象的内存地址。

实际上，对指针的理解，只需要记住下面这句话就可以了。**将某个变量赋值给指针，实际上就是将这个变量的地址赋值给指针，或者反过来说，指针中存储了这个变量的内存地址，指向了这个变量，通过指针就能找到这个变量。**

代码 `p->next=q` 说明 p 结点中的 next 指针存储了 q 结点的内存地址。代码 `p->next=p->next->next` 表示 p 结点的 next 指针存储了 p 结点的下下一个结点的内存地址。**只要掌握了指针或引用的概念，就应该可以很轻松地看懂链表代码。**

### 技巧二：警惕指针丢失和内存泄露

* 在写链表代码的时候，一定注意不要弄丢了指针。
* 对于有些语言来说，如 C 语言，内存管理是由程序员负责的，如果没有手动释放结点对应的内存空间，就会产生内存泄露。所以，在插入结点时，一定要注意操作的顺序。
* 同理，**删除链表结点时，也一定要记得手动释放内存空间。否则也会出现内存泄露问题。**

### 技巧三：利用哨兵简化实现难度

针对链表的插入、删除操作，需要对插入第一个结点和删除最后一个结点的情况进行特殊处理。这样代码实现起来就会很繁琐，不简洁，而且也容易因为考虑不全而出错。**我们可以利用「哨兵」来解决链表的边界问题，不直接参与业务逻辑。**

如果我们引入哨兵结点，在任何时候，不管链表是不是空，head 指针都会一直指向这个哨兵结点。这种带有哨兵结点的链表叫**带头链表**，相反，没有哨兵结点的链表就叫作**不带头链表**。

![带头链表](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181007162011.png)

实际上，在很多代码实现中都有用到利用哨兵来简化编程难度的技巧，如插入排序、归并排序、动态规划等。接下来再举一个非常简单的例子：

```c
// 代码一
int find(char* a, int n, char key) {
    int i = 0;
    while (i < n) {
        if (a[i] == key) {
            return i;
        }
        ++i;
    }
    return -1;
}
```

```c
// 代码二
int find(char* a, int n, int key) {
    if (a[n-1] == key) {
        return n-1;
    }
    char tmp = a[n-1];
    a[n-1] = key;
    int i = 0;
    while (a[i] != key) {
        ++i;
    }
    a[n-1] = tmp;
    if (i == n-1) {
        return -1;
    }
    return i;
}
```

对比以上两段代码，在字符串 a 很长的时候，比如几万、几十万，哪段代码运行得更快点呢？答案是代码二，我们通过一个哨兵 `a[n-1]=key` 成功省掉了一个比较语句 `i<n`，不要小看这一条语句，当累积执行上万次、几十万次时，累积的时间就很明显了。**当然，大多数情况下，我们并不需要如此追求极致的性能，而牺牲代码的可读性。（代码二的可读性太差，不推荐）**

### 技巧四：重点留意边界条件处理

要实现没有 Bug 的链表代码，一定要在编写的过程中以及编写完成之后，检查边界条件是否考虑全面，以及代码在边界条件下是否能正确运行。常用来检查链表代码是否正确的边界条件有如下几个：

* 如果链表为空时，代码是否能正常工作？
* 如果链表只包含一个结点时，代码是否能正常工作？
* 如果链表只包含两个结点时，代码是否能正常工作？
* 代码逻辑再处理头结点和尾结点的时候，是否能正常工作？
* ......

当然，边界条件不止以上列举的这些。针对不同的场景，可能还有特定的边界条件，这需要针对实际情况具体分析。

### 技巧五：举例画图，辅助思考

找一个具体的例子，把它画在纸上，释放一些脑容量，留更多的空间给逻辑思考，这样就会感觉到思路清晰很多。

比如往单链表中插入一个数据的操作，可以把各种情况都举一个例子，画出插入前和插入后的链表变化，如图所示。

![写链表代码举例画图法](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20181007160844.png)

此外，当我们写完代码之后，也可以举几个例子，画在纸上，照着代码走一遍，很容易就能发现代码中的 Bug。

### 技巧六：多写多练，没有捷径

即使已经理解并掌握了上述五个技巧，但是手写链表代码还是会出现各种各样的错误，也不要着急，这种状况会持续一段时间。需要坚持，耐心的把常见的链表操作都自己从头多谢几遍，出问题就一点一点调试，孰能生巧。**无他，唯手熟尔！**

* 单链表翻转
* 链表中环的检测
* 两个有序的链表合并
* 删除链表倒数第 n 个结点
* 求链表的中间结点

### 内容小结

* 分享写出正确链表代码的六个技巧
    * 理解指针或引用的含义
    * 警惕指针丢失和内存泄露
    * 利用哨兵简化实现难度
    * 重点留意边界条件处理
    * 举例画图，辅助思考
    * 多写多练，没有捷径
* 写链表代码是最考验逻辑思维能力的。
    * 链表代码到处都是指针的操作、边界条件的处理，非常容易产生 Bug
    * 链表代码写得好坏，课程看出一个人写代码是否足够细心，考虑问题是否全面，思维是否缜密
    * 手写链表代码是面试官非常喜欢靠的代码题。

### 课后思考

你是否还能想到其他场景，利用哨兵可以大大地简化编码难度？

## 08 | 栈：如何实现浏览器的前进和后退功能？

## 09 | 队列：如何实现线程池等有限资源池的请求派对功能？

## 10 | 递归：如何用三行代码实现查找「最终推荐人」功能？

## 11 | 排序：如何用快排思想 O 时间复杂度查找第 Kth 元素？

## 12 | 线性排序：如何根据年龄给 100 万用户数据排序？

## 13 | 排序优化：如何实现一个通用的高性能的排序函数？

## 14 | 二分查找：如何快速定位 IP 对应的省份地址？

## 15 | 跳表：为什么  Redis 一定要用跳表实现有序集合？

## 16 | 散列表（上）：如何实现 Word 文档的单词拼写检查功能？

## 17 | 散列表（下）：如何打造一个工业级水平的散列表？

## 18 | 哈希算法：如何防止数据库的用户信息被拖库？

## 19 | 二叉树：有了如此高效的散列表为什么还要用二叉树？

## 20 | 堆与优先级队列：如何寻找 TOP 10 热门搜索关键词？

## 21 | 图的表示：如何存储微博、微信等社交网络中的好友关系？

## 22 | 数据结构序列化：如何在数据库中存储一棵多级目录树？

## 23 | 深度和广度优先搜索：如何找出社交网络中的三度好友关系？

## 24 | 字符串匹配：如何用多模式串匹配实现敏感词过滤功能？

## 25 | Trie 树：如何实现搜索引擎的搜索关键词提示功能？

## 26 | 贪心算法：如何用贪心算法实现 Huffman 压缩编码？

## 27 | 分治算法：谈一谈大规模计算框架 MapReduce 中的分治思想？

## 28 | 回溯算法：从电影《蝴蝶效应》中学习回溯算法的核心思想

## 29 | 动态规划（上）：如何巧妙解决双十一购物时的凑单问题？

## 30 | 动态规划（下）：如何将 DP 状态转移方程转化为 DP 代码？