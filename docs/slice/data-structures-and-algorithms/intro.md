# 入门篇

> 为工程师量身打造的数据结构与算法私教课

![](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20180924114946.png)

## 开篇词 | 从今天起，跨过「数据结构与算法」这道坎

* 9 月 21 日起正式更新，每周一三五更新
* 每节课开篇都有思考题，课后也会有思考题
* 池建强：数据结构和算法是程序员的金线，一个普通程序员和一个优质高潜程序员的永远区分线。

### 关于作者

* 王争：毕业于西安交通大学计算机专业，前 Google 工程师。
* 学习数据结构与算法的经历：研究生时，**对算法的「迷恋」一发不可收拾，并如饥似渴**地把图书馆里几乎所有数据结构和算法的书籍都读了一遍。
* **常常边读边练。**久而久之，写代码时会考虑到性能方面的问题，算法和编程能力都有了质的飞跃。
* 得益于此，研究生毕业后，进入 Google 从事 Google 翻译相关的开发工作。

### 你并不孤独

* 你可能的情况
    * 从学校开始，就觉得数据结构难学，然后一直也没认真学？
    * 工作中，一遇到数据结构又自发本能地迅速避让，看起来无关大局？
    * 工作面试时，发现自己的基础跟不上别人的节奏？

* 沉下心打基础

腾讯 T4 的技术大牛，在腾讯工作了 10 多年，长期负责收集 QQ 后台整体建设。经历了手机 QQ 从诞生到亿级用户在线的整个过程。后来去微众银行做区块链，不到半年就摸清楚了整个技术脉络。如今，他已是微众银行的区块链负责人，微众科技创新产品的老总。

他发现，那些所谓的新技术，核心和本质的东西其实就是当初学的那些只是。掌握了这个「规律」之后，他学任何东西都很快，任何新技术都能快速迎头赶上。这就是他快速学习并且获得成功的秘诀。**基础知识就像是一座大楼的地基，它决定了我们的技术高度。而要想快速做出点事情，前提条件一定是基础能力过硬，「内功」要到位。**

### 专栏定位

* 现状
    * 经典书籍如《算法导论》，虽然很全面，但是过于理论，学起来非常枯燥；
    * 很多课程大多缺乏真实的开发场景，费劲学完感觉好像还是用不上，过不了几天就忘了。
* 专栏尝试
    * 做一个让你能真正受用的数据结构与算法课程。希望给你指明一个简洁、高效的学习路径，教你一个学习基础知识的通用方法。
* 专栏设计
    1. 根据研读数十本算法书籍和多年项目开发的经验，在众多的数据结构和算法中，精选了最实用的内容进行讲解
    2. 不只会教你怎么用，还会告诉你我们为什么需要这种数据结构和算法，一点一点帮你捋清他们背后的设计思想，培养你举一反三的能力。
    3. 对于每种数据结构和算法，都会结合真实的软件开发案例来讲解，让你知道，数据结构和算法，究竟应该如何应用到实际的编码中。
* 模块
    * 入门篇：时间和空间复杂度分析 **2节**
        * 掌握时间和空间复杂度的概念
        * 大 O 表示法的由来
        * 各种复杂度分析技巧
        * 最好、最坏、平均和均摊复杂度分析方法
    * 基础篇：专栏中篇幅最大的内容，学习重点 **26节**
    * 高级篇：讲述不太常用的数据结构和算法，开拓视野，强化训练算法思维和逻辑思维
    * 实战篇：围绕数据结构和算法再具体软件实践中的应用来讲的，通过实战部分串讲前面的数据结构和算法。通过一些开源项目、框架或者系统设计问题，剖析它们背后的数据结构和算法。

人生路上，我们会遇到很多的坎。跨过去，你就可以成长，跨不过去就是困难和停滞。**既然数据结构和算法这个坎，我们总归要跨过去，为什么不是现在呢？**

## 01 | 为什么要学习数据结构和算法？

* 想要通关大厂面试，千万别让数据结构和算法拖了后腿
    * 不管是校招还是社招，越是厉害的公司，越是注重考查数据结构与算这类基础知识。
    * 我们学习任何知识都是为了「用」的，是为了解决实际工作问题的。
* 业务开发工程师，你真的愿意做一辈子 CRUD boy 吗？
    * 作为业务开发工程师，大多数都只是调用封装好的接口、类库来堆砌代码，翻译业务逻辑。**很少需要自己实现数据结构和算法，但不需要自己实现，并不代表什么都不需要了解。**
    * 如果不懂这些类库背后的原理，不懂得时间和空间复杂度分析，你如恶化能用好、用对它们？如何选用更合适的数据结构，如何评估代码的性能和资源的小号呢？
    * 在业务开发所用到的各种框架、中间件和底层系统如 Spring、RPC 框架、消息中间件、Redis 等。**这些基础框架中，一般都糅合了很多基础数据结构和算法的设计思想。**
    * 如常用的 Key-Value 数据库 Redis 中，有序集合是用什么数据结构来实现的呢？为什么要用跳表来实现呢？为什么不用二叉树呢？
    * 若你能弄明白这些底层原理，你就能更好地使用它们。掌握数据结构和算法，不管对于阅读框架源码，还是理解其背后的设计思想，都是非常有用的。
* 基础架构研发工程师，写出达到开源水平的框架才是你的目标
    * 不同的公司、不同的人做出的 RPC 框架，架构设计思路都差不多，最后实现的功能也都差不多。但有些人做出来的框架，Bug 很多、性能一般，扩展性也不好，而有的人做的框架可以开源到 GitHub 上给很多人用，甚至被 Apache 收录。
    * 高手之间的竞争其实就在细节。这些细节包括：你用的算法是不是够优化数据存储的效率是不是够高，内存是不是够节省等等。
* 对编程还有追求？不想被行业淘汰？那就不要只会写凑合能用的代码
    * 何为编程能力强？
    * 有的人写代码的时候，从来都不考虑非功能性的需求，只是完成功能，凑合能用就好，做事情的时候，也从来没有长远规划，只把眼前的事情做好就满足了。
    * 数据结构和算法，如果你不去学，可能真的这辈子都用不到，也感受不到它的好。
* **内容小结**
    * 学习数据结构和算法，并不是为了死记硬背几个知识点。我们需要建立时间和空间复杂度意识，写出高质量的代码，能够设计基础架构，提升编程技能，训练逻辑思维，积攒人生经验，以此获得工作汇报，实现你的价值，完善你的人生。
    * **掌握了数据结构和算法，你看待问题的深度，解决问题的角度就会完全不一样。**数据结构与算法，会为你的编程之路，甚至人生之路打开一扇通往新世界的大门。
* 课后思考
    * 你为什么要学习数据结构和算法呢？的过去的软件开发中，数据结构和算法在哪些地方帮到了你？

* 精选留言
    * 为什么学习数据结构和算法？
        1. 能够写出性能更优的代码
        2. 算法是一种解决问题的思路和方法，有机会应用到生活和事业的其他方面
        3. 长期来看，大脑思考能力是个人最重要的核心竞争力，而算法是为数不多的能够有效训练大脑思考能力的途径之一。
    * 一定要动手写。
    * 学技术必须要拿出十年磨一剑的精神，从头开始。

## 02 | 如何抓住重点，系统高效地学习数据结构与算法？

实际上，数据结构和算法的东西并不多，常用的、基础的知识点更是屈指可数。只要掌握了正确的学习方法，学起来并没有看出去那么难，更不需要什么高智商、后弟子。

### 什么是数据结构？什么是算法？

* 从广义上讲，数据结构就是指一组数据的存储结构。算法就是操作数据的一组方法。
* 从狭义上讲，是指某些著名的数据结构和算法，比如队列、栈、堆、二分查找、动态规划等。
* 数据结构和算法是相辅相成的。数据结构是为算法服务的，算法要作用在特定的数据结构之上。

### 学习这个专栏需要什么基础？

* 只要有高中数学水平就完全可以学习。
* 最好有些编程基础，如果有项目经验就更好。
* 对于每个概念和实现过程，都会从实际场景出发， 不仅教你「是什么」，还会教你「为什么」，并且告诉你遇到同类型问题应该「怎么做」。

### 学习的重点在什么地方？

> 梳理一下，应该先学什么，后学什么。可以对照看看，你属于哪个阶段，然后有针对地进行学习。

* 首先要掌握一个数据结构与算法中最重要的概念：**复杂度分析**。
    * 几乎占了数据结构和算法这门课的半壁江山，是数据结构和算法学习的精髓。
    * 复杂度分析会用很大篇幅来讲透，你也一定要花大力气来啃，必须要拿下，并且要搞得非常熟练，否则后面的内容也很难学好。
* 数据结构和算法知识点导图
    * 复杂度分析
        * 空间复杂度
        * 时间复杂度
            * 最好
            * 最坏
            * 平均
            * 均摊
    * 基本算法思想
        * 贪心算法
        * 分治算法
        * 动态规划
        * 回溯算法
        * 枚举算法
    * 排序
        * $O(n^2)$
            * 冒泡排序
            * 插入排序
            * 选择排序
            * 希尔排序
        * $O(nlog(n))$
            * 归并排序
            * 快速排序
            * 堆排序
            * 二叉排序树排序
        * $O(n)$
            * 计数排序
            * 基数排序
            * 桶排序
    * 搜索
        * 深度优先搜索 DFS
        * 广度优先搜索 BFS
        * $A^*$ 启发式搜索
    * 查找
        * 线性表查找
        * 树结构查找
        * 散列表查找
    * 线性表
        * 数组
        * 链表
            * 单向链表
            * 双向链表
            * 循环链表
            * 双向循环链表
            * 静态链表
        * 栈
            * 顺序栈
            * 链式栈
        * 队列
            * 普通队列
            * 双端队列
            * 阻塞队列
            * 并发队列
            * 阻塞并发队列
    * 散列表
        * 散列函数
        * 冲突解决
            * 链表法
            * 开发寻址
            * 其他
        * 动态扩容
        * 位图
    * 树
        * 二叉树
            * 平衡二叉树
            * 二叉查找树
            * 平衡二叉查找树
                * AVL 树
                * 红黑树
            * 完全二叉树
            * 满二叉树
        * 多路查找树
            * B 树
            * B+ 树
            * 2-3 树
            * 2-3-4 树
        * 堆
            * 小顶堆
            * 大顶堆
            * 优先级队列
            * 斐波那契堆
            * 二项堆
    * 字符串匹配
        * 朴素
        * KMP
        * Robin-Karp
        * Boyer-Moore
        * AC 自动机
        * Trie
    * 其他
        * 数论
        * 计算几何
        * 概率分析
        * 并查集
        * 拓扑网络
        * 矩阵运算
        * 线性规划

作为初学者，或一个非算法工程师来说，你并不需要掌握图里面的所有知识点。很多高级的数据结构和算法，如二分图、最大流等，这些在平常开发中很少会用到。所以，你暂时可以不用看。**学习要学会找重点。如果不分重点地学习，眉毛胡子一把抓，学起来肯定会被比较吃力。

结合学习心得、多年的面试和开发经验，总结了 20 个最常用的、最基础的数据结构算法，**不管是应付面试还是工作需要，只要集中精力逐一攻克这 20 个知识点就足够了。**

* 10 个数据结构：数组、链表、栈、队列、散列表、二叉树、堆、跳表、图、Trie 树。
* 10 个算法：递归、排序、二分查找、搜索、哈希算法、贪心算法、分治算法、回溯算法、动态规划、字符串匹配算法。

在学习数据结构和算法的过程中，你也要注意，不要只是死记硬背，不要为了学习而学习，而是**要学习它的「来历」、「自身的特点」、「适合解决的问题」以及「实际的应用场景」**。

学习数据结构和算法的过程，是非常好的思维训练的过程，所以，千万不要被动地记忆，要多辩证地思考，多问为什么。

### 一些可以让你事半功倍的学习技巧

* **边写边练，适度刷题。**
    * 建议每周花 1-2 个小时的时间，集中把这周的三节内容涉及的数据结构和算法，全都自己写出来，用代码实现一遍。
    * **可以「适度」刷题，但一定不要浪费太多时间在刷题上。**我们学习的目的还是掌握，然后应用。
    * 只有面试 FLAG 这样的工程，它们的算法题目非常非常难的，必须大量刷题，才能在短期内提升应试正确率。
* **多问、多思考、多互动**
    * 学习最好的方法是，找到几个人一起学习，一块儿讨论切磋，有问题及时寻求老师答疑。
* **打怪升级学习法**
    * 学习的过程中，碰到的最大问题就是坚持不下来。
    * 在枯燥的学习过程中，也可以给自己设立一个切实可行的目标，就像打怪升级一样。
    * 如每节课后都写一篇学习笔记或新的，也可以尝试找出每节课中讲的不对、不合理的地方
* **知识需要沉淀，不要想试图一下子掌握所有**
    * 想听一遍、看一遍就把所有知识点掌握，这肯定是不可能的。**学习知识的过程是反复迭代、不断沉淀的过程。

### 内容小结

* 划了数据结构和算法的学习重点，复杂度分析，以及 10 个数据结构和 10 个算法
* 分享了一些学习技巧和方法：边学边练、多问、多思考，打怪升级和沉淀法
* 最重要的就是：一定要好好实践。

### 课后思考

* 对照上面讲的「打怪升级学习法」，思考一下你自己学习这个专栏的方法。
* 另外，在之前学习数据结构和算法的过程中，遇到过什么样的困难和疑惑吗？

## 03 | 复杂度分析（上）：如何分析、统计算法的执行效率和资源消耗？

![](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20180927103600.png)

数据结构和算法本身解决的是「快」和「省」的问题，即如何让代码运行得更快，如何让代码更省存储空间。所以，执行效率是算法的一个非常重要的考量指标。**复杂度分析是整个算法学习的精髓，只要掌握了它，数据结构和算法的内容基本上就掌握了一半。**

### 为什么需要复杂度分析？

思考为什么不直接把代码跑一遍，然后通过统计、监控，就能得到算法执行的时间和占用的内存大小。这种评估算法执行效率的方法是正确的，被称为**事后统计法**，但是有非常大的局限性。

1. 测试结果非常依赖测试环境：测试环境中硬件的不同会对测试结果有很大的影响。
2. 测试结果手数据规模的影响很大：如对于小规模的数据排序，插入排序可能反倒会比快速排序要快。

所以，**我们需要一个不用具体的测试数据来测试，就可以粗略地估计算法的执行效率的方法。**这就是时间和空间复杂度分析法。

### 大 O 复杂度表示法

算法的执行效率，粗略来讲，就是算法代码执行的时间。

```java
int cal(int n) {
    int sum = 0;
    int i = 1;
    for (; i <= n; ++i) {
        sum = sum + i;
    }
    return sum;
}
```

从 CPU 的角度来看，以上代码的每一行都执行着类似读数据 -> 运算 -> 写数据的操作。虽然每行代码对应的 CPU 执行的个数和执行的时间都不一样，但若只是粗略估计的话，可以假设每行代码执行的时间都一样，为一个单位时间（unit_time）。在这个假设的基础上， 可以估算上述代码的总执行时间。

* 第 2、3 行代码分别需要 1 个 unit_time 的执行时间
* 第 4、5 行代码都运行了 n 遍，所以需要 2n 个 unit_time 的执行时间
* 代码的总执行时间就是 $T(n)=O(2n+2)$ 个 unit_time。

由上可以看出，**所有代码的执行时间 T(n) 与每行代码的执行次数成正比。**

```java
int cal(int n) {
    int sum = 0;
    int i = 1;
    int j = 1;
    for (; i <= n; ++i) {
        j = 1;
        for (; j <= n; ++j) {
            sum = sum + i * j;
        }
    }
}
```

* 第 2、3、4 行代码，每行代码都需要 1 个 unit_time 的执行时间
* 第 5、6 行代码循环执行了 n 遍，需要 2n 个 unit_time 的执行时间
* 第 7、8 行代码循环执行了 $n^2$ 遍，需要 $2n^2$ 个 unit_time 的执行时间
* 整段代码总的执行时间 $T(n) = O(2n^2+2n+3)$ 个 unit_time。

由以上两段代码执行时间的推导过程，我们可以得到一个非常重要的规律：**所有代码的执行时间 T(n) 与每行代码的执行次数 n 成正比。**将这个规律总结成一个公式即：

$$T(n) = O(f(n))$$

其中，T(n) 表示代码执行的时间；n 表示数据规模的大小；f(n) 表示每行代码执行的次数综合。O 表示代码的执行时间 T(n) 与表达式 f(n) 成正比。

以上就是**大 O 时间复杂度表示法**，实际上它并不具体表示代码真正的执行时间，而是表示**代码执行时间随数据规模增长的变化趋势**。所以也叫做**渐进时间复杂度（Asymptotic Time Complexity），简称时间复杂度**。

当 n 很大时，公式中的低阶、常量、系数三部分并不左右增长趋势，所以都可以忽略。我们只需要记录一个最大量级即可。用大 O 表示法来分别表示上述两段代码的时间复杂度，就可以记为：$T(n) = O(n)$，$T(n) = O(n^2)$。

### 时间复杂度分析

如何分析一段代码的时间复杂度呢？以下有三个非常实用的方法：

#### 1. 只关注循环执行次数最多的一段代码

在分析一个算法、一段代码的时间复杂度的时候，也只关注循环次数最多的那一段代码即可。这段核心代码执行次数的 n 的量级，就是整段要分析代码的时间复杂度。

#### 2. 加法法则：总复杂度等于量级最大的那段代码的复杂度

```java
int cal(int n) {
    int sum_1 = 0;
    int p = 1;
    for (; p < 100; ++p) {
        sum_1 = sum_1 + p;
    }

    int sum_2 = 0;
    int q = 1;
    for (; q < n; ++q) {
        sum_2 = sum_2 + q;
    }

    int sum_3 = 0;
    int i = 1;
    int j = 1;
    for (; i <= n; ++i) {
        j = 1;
        for (; j <= n; ++j) {
            sum_3 = sum_3 + i * j;
        }
    }

    return sum_1 + sum_2 + sum_3;
}
```

综合分析以上三段代码的时间复杂度（依次为 $O(1)$, $O(n)$, $O(n^2)$），取其中最大的量级即可得到整段代码的时间复杂度为 $O(n^2)$。**也就是说，总的时间复杂度等于量级最大的那段代码的时间复杂度。**将这个规律抽象成公式就是：

* 如果 $T_1(n) = O(f(n)), T_2(n) = O(g(n))$
* 那么 $T(n) = T_1(n) + T_2(n) = max(O(f(n)), O(g(n))) = O(max(f(n), g(n)))$

#### 3. 乘法法则：嵌套代码的复杂度等于嵌套内外代码复杂度的乘积

* 如果 $T_1(n) = O(f(n)), T_2(n) = O(g(n))$
* 那么 $T(n) = T_1(n) * T_2(n) = O(f(n)) * O(g(n)) = O(f(n) * g(n))$

落实到具体的代码上，可以把乘法法则看成是**嵌套循环**。如下代码所示：

```java
int cal(int n) {
    int ret = 0;
    int i = 1;
    for (; i < n; ++i) {
        ret = ret + f(i);
    }
}

int f(int n) {
    int sum = 0;
    int i = 1;
    for (; i < n; ++i) {
        sum = sum + i;
    }
    return sum;
}
```

以上代码中 `cal()` 函数的时间复杂度就是 $T(n) = T_1(n) * T_2(n) = O(n * n) = O(n^2)$。

以上所讲到的三种复杂度的分析技巧，并不用可以记忆，复杂度分析关键在于「熟练」，只要多看案例，多分析，就能做到「无招胜有招」。


### 几种常见的时间复杂度实例分析

![](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20180927160205.png)

对于以上的复杂度量级，可以粗略地分为两类：**多项式量级和非多项式量级**。其中，非多项式量级只有两个：$O(2^n)$ 和 $O(n!)$。

我们把时间复杂度为非多项式量级的算法问题叫作 NP (Non-Deterministic Polynomial，非确定多项式) 问题。当数据规模 n 越来越大时，非多项式量级算法的执行时间会急剧增加，求解问题的执行时间会无限增长。因此，非多项式时间复杂度算法其实是非常低效的算法。

* 常量阶 $O(1)$：只要代码的执行时间不随 n 的增长而最大，这样代码的时间复杂度都记住 $O(1)。**一般情况下，只要算法中不存在循环语句、递归语句，即使有成千上万行的代码，其时间复杂度也是 $O(1)$。
* 对数阶 $O(logn)$、线性对数阶 $O(nlogn)$：对数阶时间复杂度非常常见，同时也是最难分析的一种时间复杂度。**在对数阶时间复杂度的表示方法里，我们会忽略对数的「底」，统一表示为 $O(logn)$。**

```java
i = 1;
while (i <= n) {
    i = i * 2;
}
```

* $O(m+n)$、$O(m*n)$：代码的复杂度由两个数据的规模来决定。
    * 如下段代码中，m 和 n 是表示两个数据规模，无法事先评估 m 和 n 谁的量级大，所以表示复杂度的时候不能简单地利用加法法则来省略掉其中一个，所以其时间复杂度是 $O(m+n)$。
    * 原来的加法规则就需要改为：$T_1(m) + T_2(n) = O(f(m) + g(n))$，但是乘法法则依然有效：$T_1(m) * T_2(n) = O(f(m) * f(n))$.

```java
int cal(int m, int n) {
    int sum_1 = 0;
    int i = 1;
    for (; i < m; ++i) {
        sum_1 = sum_1 + i;
    }

    int sum_2 = 0;
    int j = 1;
    for (; j < n; ++j) {
        sum_2 = sum_2 + j;
    }

    return sum_1 + sum_2;
}
```

### 空间复杂度分析

理解了时间复杂度分析法，类似的，空间复杂度分析法就非常简单了。空间复杂度全称是**渐进空间复杂度（Asymptotic Space Complexity），表示算法的存储空间与数据规模之间的增长关系。**

```java
void print(int n) {
    int i = 0; // 申请空间存储变量 i，常量阶
    int[] a = new int[n]; // 申请大小为 n 的 int 类型数组，线性阶
    for (i; i<n; ++i) {
        a[i] = i * i;
    }

    for (i = n-1; i >= 0; --i) {
        print out a[i]
    }
}
```

我们常见的空间复杂度就是 $O(1)$、$O(n)$、$O(n^2)$，像 $O(logn)$、$O(nlogn)$ 这样的对数阶复杂度平时一般用不到。空间复杂度分析比时间复杂度分析要简单很多。

### 内容小结

![](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20180927173050.png)

* 复杂度也叫渐进复杂度，包括时间复杂度和空间复杂度，用来分析算法执行效率与数据规模之间的增长关系，可以粗略地说，越高阶复杂度的算法，执行效率越低。
* 常见的复杂度从低阶到高阶有：$O(1)$, $O(logn)$, $O(n)$, $O(nlogn)$, $O(n^2)$。
* **复杂度分析并不难，关键在于多练。**

### 课后思考

有人说，我们项目之前都会进行性能测试，再做代码的时间复杂度、空间复杂度分析，是不是多此一举呢？而且，每段代码都分析一下时间复杂度、空间复杂度，是不是很浪费时间呢？你怎么看待这个问题呢？

### 精选留言

* 渐进时间复杂度、空间复杂度分析与性能基准测试并不冲突，而是相辅相成的。但低阶时间复杂度程序有极大可能性会优于高阶的时间复杂度程序，所以实际编程中，时刻关心理论时间复杂度和空间复杂度模型有助于产出效率更高的程序。重点在于编程时需要培养这种复杂度分析思维。
* 性能测试是依附于具体环境的如 SIT、UAT 机器配置及实例数量等。复杂度分析是独立于环境的，可以大致估算出程序所执行的效率。

## 04 | 复杂度分析（下）：详解最好、最坏、平均、均摊复杂度分析

四个复杂度分析方面的知识点：最好情况时间复杂度（best case time complexity）、最坏情况时间复杂度（worst case time complexity）、平均情况时间复杂度（average case time complexity）和均摊时间复杂度（amortized time complexity）。

### 最好、最坏情况时间复杂度

```java
// 在一个无需的数组 array 中查找变量 x 出现的位置，若没有找到则返回 -1
// n 表示数组 array 的长度
int find(int[] array, int n, int x) {
    int i = 0;
    int pos = -1;
    for (; i<n; i++) {
        if (array[i] == x) {
            pos = i;
        }
    }
    return pos;
}
```

```java
// 更高效的写法：有可能中途找到就可以提前结束循环
// n 表示数组 array 的长度
int find(int[] array, int n, int x) {
    int i = 0;
    int pos = -1;
    for (; i<n; i++) {
        if (array[i] == x) {
            pos = i;
            break;
        }
    }
    return pos;
}
```

* 如果数组中的第一个元素正好是要查找的变量 x，那就不需要继续遍历剩下的 n-1 个数据，则时间复杂度就是 O(1)。
* 如果数组中不存在变量 x，那就需要把整个数组都遍历一遍，时间复杂度就成了 O(n)。
* 所以，在不同的情况下，这段代码的时间复杂度是不一样的。

因此，为了表示代码在不同情况下的不同时间复杂度，我们需要引入三个概念：**最好情况时间复杂度、最坏情况时间复杂度和平均情况时间复杂度。**

* 最好情况时间复杂度：在最理想的情况下，执行这段代码的时间复杂度。
* 最坏情况时间复杂度：在最糟糕的情况下，执行这段代码的时间复杂度。

### 平均情况时间复杂度

通过上述查找变量 x 的例子来解释：要查找的变量 x 在数组中的位置，有 n+1 中情况，**在数组的 0-n-1 位置中和不在数组中。**我们把每种情况下，查找需要遍历的元素个数累加起来，然后再除以 n+1，就可以得到需要遍历的元素个数的平均值，即：$(1+2+3+...+n+n)/(n+1)=n(n+3)/2(n+1)$。根据时间复杂度的大 O 表示法，可以省略掉稀疏、低阶和常量， 所以公式简化之后即可得到平均时间复杂度就是 O(n)。

如果我们把每种情况发生的概率考虑进去，那平均情况时间复杂度的计算：$1*(1/2n)+2*(1/2n)+3*(1/2n)+...+n*(1/2n)+n*(1/2)=(3n+1)/4$。这个值就是概率论中的加权平均值，也叫做期望值，所以平均时间复杂度的全称应为加权平均时间复杂度或期望时间复杂度。

实际上，在大多数情况下，我们并不需要区分最好、最坏、平均情况时间复杂度三种情况。只有在同一块代码在不同的情况下，时间复杂度有量级的差距，我们才会使用这三种时间复杂度表示法来区分。

### 均摊时间复杂度

均摊时间复杂度的应用场景比平均情况时间复杂度更加特殊，更加有限。为了方便讲解，通过以下一段代码来帮助理解：

```java
// array 表示一个长度为 n 的数组
// 代码中的 array.length 就等于 n
int[] array = new int[n];
int count = 0;

void insert(int val) {
    if (count == array.length) {
        int sum = 0;
        for (int i = 0; i < array.length; ++i) {
            sum = sum + array[i];
        }
        array[0] = sum;
        count = 1;
    }

    array[count] = val;
    ++count;
}
```

代码解释：实现了一个往数组中插入数据的功能。当数组满了之后，也就是戴安中的 `count == array.length` 时，我们用 for 循环遍历数组求和，并清空数组，将求和之后的 sum 值放到数组的第一个位置，然后再讲新的数据插入。但如果数组一开始就有空间空间，则直接将数据插入数组。

* 最理想的情况下，数组中有空闲空间，只需要将数据插入到数组下标为 count 的位置就可以，最好情况时间复杂度为 O(1)。
* 最坏的情况下，数组中没有空闲空间了，我们需要先做一次数组的遍历求和，然后再将数据插入，所以最坏情况的时间复杂度为 O(n)。
* 平均情况时间复杂度：假设数组长度为 n，根据数据插入的位置不同，我们可以分为 n 中情况，每种情况的时间复杂度是 O(1)。此外，还有一种例外情况，就是在数组没有空闲空间插入一个数组，这时的时间复杂度是 O(n)。并且，这 n+1 种情况发生的概率一样，都是 1/(n+1)。所以根据加权平均的计算方法，求得平均复杂度就是：$(1+1+1+...+n)*(1/(n+1))=O(1)$。
* 均摊时间复杂度：每一次 O(n) 的插入操作，都会跟着 n-1 次 O(1) 的插入操作，把耗时多的那次操作均摊到接下来的 n-1 次耗时少的操作上，均摊下来，这一组连续的操作的均摊时间复杂度就是 O(1)。

均摊时间复杂度和摊还分析的应用场景：对一个数据结构进行一组连续操作中，大部分情况下时间复杂度都很低，只有个别情况下时间复杂度比较高，而且这些操作之间存在前后连贯的时序关系，这个时候，我们就可以将一组操作放在一块儿分析，看是否能将较高时间复杂度那次操作的耗时，平摊到其他那些时间复杂度比较低的操作上。而且，**在能够应用均摊时间复杂度分析的场合，一般均摊时间复杂度就等于最好情况时间复杂度。**均摊时间复杂度就是一种特殊的平均时间复杂度，没必要花太多精力去区分它们。**最应该掌握的是它的分析方法，摊还分析。**

### 内容小结

* 学习复杂度分析相关的几个概念：最好情况时间复杂度、最坏情况时间复杂度、平均情况时间复杂度、均摊时间复杂度。
* 最好和最坏情况下的时间复杂度分析起来比较简单，但平均和均摊两个复杂度分析相对比较复杂，需要深入理解并慢慢实践。

### 课后思考

用今天学到的知识来分析下面这个 add() 函数的时间复杂度。

```java
// 全局变量，大小为 10 的数组 array，长度 len，下标 i
int array[] = new int[10];
int len = 10;
int i = 0;

// 往数组中添加一个元素
void add(int element) {
    if (i >= len) { // 数组空间不够了
        // 重新申请一个 2 倍大小的数组空间
        int new_array[] = new int[len*2];
        // 把原来 array 数组中的数据一次 copy 到 new_array
        for (int j = 0; j < len; ++j) {
            new_array[j] = array[j];
        }
        // new_array 复制给 array，array 现在大小就是 2 倍 len 了
        array = new_array;
        len = 2 * len;
    }
    // 将 element 放到下标为 i 的位置，下标 i 加一
    array[i] = element;
    ++i;
}
```

* 最好情况时间复杂度 O(1)
* 最坏情况时间复杂度 O(len)
* 平均情况时间复杂度 O(1)
* 均摊时间复杂度 O(1)

## 周末福利第一期 | 数据结构与算法学习书单

![](http://pbw9sjeuq.bkt.clouddn.com/PicGo/20180930170604.png)

### 针对入门的趣味书

入门时，建议找一些比较容易看的书来看，比如《大话数据结构》和《算法图解》。不要太在意书写得深浅，重要的是能不能坚持看完。

* 《大话数据结构》
* 《算法图解》

这些入门书共同的问题是，缺少细节，不够系统，也不够严谨。所以，如果想要系统地学数据结构和算法，看这两本书肯定是不够的。

### 针对特定编程语言的教科书

市面上大部分数据结构和算法书籍都是用 C、C++、Java 语言实现的，还有些是用伪代码。使用 Python、Go、PHP、JavaScript、Object-C 等这些编程语言实现的相对较少。

推荐《数据结构和算法分析》，国外很多大学采用本书作为教材。这本书非常系统、全面、严谨，而且又不是特别难，适合对数据结构和算法有些了解，并且掌握了至少一门编程语言的同学。作者用心的分别采用三种语言写了三个版本，分别是：

* 《数据结构与算法分析 ：C 语言描述》
* 《数据结构与算法分析：C++ 描述》
* 《数据结构与算法分析：Java 语言描述》

此外，如果你熟悉 Python 或 JavaScript，可以参考《数据结构与算法 JavaScript 描述》和《数据结构与算法：Python 语言描述》。

### 面试必刷的宝典

* 《剑指 Offer》这本书几乎包含了所有常见的、经典的面试题，如果能搞懂这本书的内容，应付一般公司的面试应该不成问题。
* 《编程珠玑》最大的特色是讲了很多针对海量数据的处理技巧，这个可能是其他算法书籍较少涉及到的。不管是开拓眼界，还是应付面试，这本书都很值得一看。
* 《编程之美》这本书的多位作者绝大部分都是微软的工程师，但里面的算法题稍微有点难，也不是很系统。适合有一定基础，喜欢钻研写算法问题，或者面试 Google、Facebook 这样的公司，可以拿这本书里的题来自测一下。

### 经典大部头

经典大部头都太厚了，看起来比较费劲，估计很少有人能坚持全部看下来。如果想更加深入学习数据结构和算法，还是强烈建议看看。

* 《算法导论》这本书的章节安排不是循序渐进的，里面充斥着各种算法的正确性、复杂度的证明、推导，数学公式比较多，一般人看起来比较吃力，不适合作为入门书籍。
* 《算法》相对来说友好很多，更容易看懂，更加适合初学者入门。但这本书的缺点就是内容不够全面，如动态规划完全没有涉及，数据结构相关的知识点也讲得不多，基本偏重讲算法。

### 殿堂级经典

* 《计算机程序设计艺术》这套书的深度、广度、系统性和全面性都是其他所有数据结构和算法书籍无法比拟的。你可以把它当做算法学习的终极挑战。

### 闲暇阅读

* 《算法帝国》
* 《数学之美》
* 《算法之美》

这些书的共同特点是，都列举类大量的例子，非常通俗易懂。当你看这些数的时候，你常常会深深感受到算法的力量，被算法的优美之处折服。