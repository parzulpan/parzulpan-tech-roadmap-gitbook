# 算法训练营笔记

## Dsa Camp

### 0.前言

### 1.数据结构与算法总览

#### 线上课程

三个要点：

* 预习 - 基础知识自己预习和查看
* 课堂互动 - 跟着老师一起思路、回答并解决问题
* 课后作业 - 按照切题方法

#### 期待效果

三个效果：

* 职业级别 - 对于数据结构和算法的理解
* 通过大厂算法面试
* LeetCode 解题数的积累

#### 如何精通一个领域

**1.Chunk it up 切碎知识点**

何为 切碎知识点，即庖丁解牛和脉络连接。

任何一个知识体系都是一棵树，如果要掌握某个领域的关键知识，就需要将知识变成一颗树状结构。有最基本的根，然后分出主干、分出枝叶。最后每个知识点和你所熟悉的知识挂靠在一起，成为树状结构。

> 人脑不适合记忆、理解孤立的知识，脑图有助于理解。 --- Elon Musk（引自reddit）

**数据结构**：

* 一维：
  * 基础：数组 Array、链表 LinkedList
  * 高级：栈 Stack、队列 Queue、双端队列 Deque、集合 Set、映射 Map
* 二维：
  * 基础：树 Tree、图 Graph
  * 高级：二叉搜索树 BinarySearchTree、红黑树 RedBlackTree、堆 Heap、并查集 DisjointSet、字典树 Trie
* 特殊：
  * 位算法 Bitwise、布隆过滤器 BloomFilter
  * LRU Cache

需要了解每个数据结构的原理和代码框架。

***

**算法**：

* if-else、switch -> branch
* for、while loop -> iteration
* recursion -> divide conquer、backtrace
* search -> depth first search、breadth first search、A\*
* dynamic programming
* binary search
* greedy
* math
* geometry

需要掌握每种算法的思想和代码模板。

**2.Deliberate Practicing 刻意练习**

**两个要点**：

* 基本功是根本
* 基础的分解训练和反复练习 - 多多重复，百炼成钢

**具体就是**：

* 刻意练习 - 至少**五遍** \*
  * 第一遍：最多五分钟读题加思考，否则直接看解法，注意需要了解多种解法以及其中差异，最后背诵默写好的解法
  * 第二遍：马上自己手撸，实时提交，多种解法比较体会，并进行优化
  * 第三遍：过了一天，再进行手撸，并且检验对多种解法的熟练程度
  * 第四遍：过了一周，再次进行手撸
  * 第五遍：面试前一周，恢复性训练
* 练习缺陷、弱点的地方
* 接受不舒服、不爽、枯燥的感觉

**3.Feedback 反馈**

**反馈分为**：

* 即时反馈
* 主动型反馈（自己去找）
  * 高手代码 GitHub、LeetCode
  * 第一视角直播
* 被动式反馈（高手给你指点）
  * code review
  * 教练看你打，给你反馈

#### 切题四件套

* clarification 反复沟通和理解题意
* possible solutions 可能的所有解法
  * compare 时间和空间复杂度
  * optimal 最佳解法
* coding 开始写吧
* test cases 测试样例能体现你的专业性

### 2.前期准备和复杂度分析

#### 一些准备

* 电脑设置
  * Google
  * Terminal
  * VSCode
  * IntelliJ
* Code Style
  * Google Code Style
  * Alibaba Code Style
  * Airbnb Code Style
* LeetCode
  * leetcode-cn.com **题解**
  * leetcode.com **Discuss most vote**
* 指法和小操作
  * 快速到行头行尾
  * 选单词、选整行、先整列
  * IDE 的自动补全
  * Top tips for xx
* 自顶向下的编程方式
  * [clean-code](https://markhneedham.com/blog/2008/09/15/clean-code-book-review/)
  * YesLeetCode 125.验证回文串

#### 时间空间复杂度

* **Big O Natation**
  *   **O(1)** Constant Complexity 常数复杂度

      ```java
      int n = 1000;
      System.out.println("Hey - your input is: " + n);
      ```
  *   **O(logn)** Logarithmic Complexity 对数复杂度

      ```java
      for (int i = 1; i < n; i = i * 2) {
          System.out.println("Hey - I'm busy looking at: " + i); 
      }
      ```
  *   **O(n)** Linear Complexity 线性时间复杂度

      ```java
      for (int i = 1; i <= n; i++) {
          System.out.println("Hey - I'm busy looking at: " + i);
      }
      ```
  *   **O(n^2)** N square Complexity 平⽅

      ```java
      for (int i = 1; i <= n; i++) {
          for (int j = 1; j <=n; j++) {
              System.out.println("Hey - I'm busy looking at: " + i + " and " + 
              j);
          } 
      }
      ```
  *   **O(n^3)** N square Complexity ⽴⽅

      ```java
      for (int i = 1; i <= n; i++) {
          for (int j = 1; j <=n; j++) {
              for (int k = 1; k <=n; k++) {
                  System.out.println("Hey - I'm busy looking at: " + i + "and" + j);
              }
          } 
      }
      ```
  * **O(2^n)** Exponential Growth 指数
  * **O(n!)** Factorial 阶乘
* **Master Theorem**
  * **O(logn)** Binary Search
  * **O(n)** Binary Tree Traversal
  * **O(n)** Optimal Sorted Matrix Search
  * **O(nlogn)** Merge Sort

### 3.数组、链表、跳表

#### 数组、链表、跳表的基本实现和特性

**数组**

**数组在工程中的应用**

**链表**

链表是一种物理存储单元上非连续、非顺序的存储结构。链表由一序列的结点（链表中的每一个元素成为结点）组成。

**单向链表**，是链表的一种，它有多个结点组成，每个结点都由一个数据域和一个指针组成，数据域用来存储数据，指针域用来指向其后结点。单链表的头结点的数据域不存储数据，指针域指向第一个真正存储数据的结点。

数据结构和算法：

* 单向链表结点的数据结构 SingleLinkedListNode
* 单向链表的算法实现 SingleLinkedList

**双向链表**，有两个指针，一个指向前一个节点，一个后一个节点。它的优点是可以找到前驱和后继，可进可退；它的缺点是 增加/删除 节点复杂，因为需要多分配一个指针存储空间。它适用于需要双向查找节点值的情况。

数据结构和算法：

* 双向链表结点的数据结构 DoubleLinkedListNode
* 双向链表的算法实现 DoubleLinkedList

**链表在工程中的应用**

**单向链表**：

* YesLeetCode 206.反转链表
* YesLeetCode 92.反转链表 II

**双向链表**：

* YesLeetCode 146.LRU 缓存
* YesLeetCode 460.LFU 缓存
* YesLeetCode 1472.设计浏览器历史记录
* YesLeetCode 432.全 O(1) 的数据结构

**跳表**

复杂度分析：

* 跳表查询的时间复杂度分析
  1. 由 n/2、n/4、n/8，则第 k 级索引结点的个数就是 **n/(2^k)**
  2. 假设索引有 h 级，最高级的索引有 2 个结点。n/(2^h) = 2，从而求得 **h = log2(n)-1**
  3. 那么跳表的高度就是 **logn**，且每层索引遍历的结点个数为 3，所以在跳表中查询任意数据的时间复杂度就是 **O(logn)**
* 跳表查询的时间复杂度分析
  1. 原始链表大小为 n，每 2 个结点抽 1 个，每层索引的结点数：n/2, n/4, n/8, 8, 4, 2
  2. 原始链表大小为 n，每 3 个结点抽 1 个，每层索引的结点数：n/3, n/9, n/27, 9, 4, 2
  3. 所以跳表的空间复杂度就是 **O(n)**

总结起来，跳表的就是 升维思想以及空间换时间。

数据结构和算法：

* 跳表的数据结构
* 跳表的算法实现

**跳表在工程中的应用**

* Redis

#### 实战题目解析

### 4.栈、队列、优先队列、双端队列

### 5.哈希表、映射、集合

### 6.树、二叉树、二叉搜索树

### 7.泛型递归、树的递归

### 8.分治、回溯

### 9.深度优先搜索、广度优先搜索

### 10.贪心算法

### 11.二分查找

### 12.动态规划

### 13.字典树、并查集

### 14.高级搜索

### 15.红黑树、AVL Tree

### 16.位运算

### 17.布隆过滤器、LRU Cache

### 18.排序算法

### 19.高级动态规划

### 20.字符串算法

### 参考

* [算法训练营第4期 GitHub 使用指南](https://shimo.im/docs/9ty8pjk6ckxGrkQt/read)
* [10月17号算法1-5班社群分享](https://shimo.im/docs/qhXjxtCyt8kgCkc6/read)
* [作业提交仓库](https://github.com/algorithm004-04/algorithm004-04)
* [DsaCamp-数据结构脑图](https://naotu.baidu.com/file/78d64abc80ed4bcf260ba723e3100b79)
* [DsaCamp-算法脑图](https://naotu.baidu.com/file/620ab93db71a7fa99be5050a4ae48043)
* [\[经验分享\] 覃超算法训练营学习笔记](https://blog.csdn.net/mouliu6141/article/details/107050849)
* [覃超-算法训练营 学习方法分享](http://t.zoukankan.com/Forgenvueory-p-13439624.html)

### 总结
