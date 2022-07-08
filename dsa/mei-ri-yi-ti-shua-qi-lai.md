# 每日一题刷起来

[LeetCode](https://leetcode.cn/u/parzulpan/)，这玩意就像做数学题似的，在掌握基础知识和一些解题模板之后，刷就完事了\~ :tada:



### 2022.07.08

[**1217. 玩筹码**](https://leetcode.cn/problems/minimum-cost-to-move-chips-to-the-same-position/)

> 有 n 个筹码。第 i 个筹码的位置是 position\[i] 。
>
> 我们需要把所有筹码移到同一个位置。在一步中，我们可以将第 i 个筹码的位置从 position\[i] 改变为:
>
> position\[i] + 2 或 position\[i] - 2 ，此时 cost = 0&#x20;
>
> position\[i] + 1 或 position\[i] - 1 ，此时 cost = 1&#x20;
>
> 返回将所有筹码移动到同一位置上所需要的 最小代价 。

思路：



编码：

```java
```

### 2022.07.07

[**648. 单词替换**](https://leetcode.cn/problems/replace-words/)

> 在英语中，我们有一个叫做 词根(root) 的概念，可以词根后面添加其他一些词组成另一个较长的单词——我们称这个词为 继承词(successor)。例如，词根an，跟随着单词 other(其他)，可以形成新的单词 another(另一个)。
>
> 现在，给定一个由许多词根组成的词典 dictionary 和一个用空格分隔单词形成的句子 sentence。你需要将句子中的所有继承词用词根替换掉。如果继承词有许多可以形成它的词根，则用最短的词根替换它。

思路：



编码：

```java
```

### 2022.07.06

[**736. Lisp 语法解析**](https://leetcode.cn/problems/parse-lisp-expression/)

> 给你一个类似 Lisp 语句的字符串表达式 expression，求出其计算结果。
>
> 表达式语法如下所示:
>
> 表达式可以为整数，let 表达式，add 表达式，mult 表达式，或赋值的变量。表达式的结果总是一个整数。 (整数可以是正整数、负整数、0) let 表达式采用 "(let v1 e1 v2 e2 ... vn en expr)" 的形式，其中 let 总是以字符串 "let"来表示，接下来会跟随一对或多对交替的变量和表达式，也就是说，第一个变量 v1被分配为表达式 e1 的值，第二个变量 v2 被分配为表达式 e2 的值，依次类推；最终 let 表达式的值为 expr表达式的值。 add 表达式表示为 "(add e1 e2)" ，其中 add 总是以字符串 "add" 来表示，该表达式总是包含两个表达式 e1、e2 ，最终结果是 e1 表达式的值与 e2 表达式的值之 和 。 mult 表达式表示为 "(mult e1 e2)" ，其中 mult 总是以字符串 "mult" 表示，该表达式总是包含两个表达式 e1、e2，最终结果是 e1 表达式的值与 e2 表达式的值之 积 。 在该题目中，变量名以小写字符开始，之后跟随 0 个或多个小写字符或数字。为了方便，"add" ，"let" ，"mult" 会被定义为 "关键字" ，不会用作变量名。 最后，要说一下作用域的概念。计算变量名所对应的表达式时，在计算上下文中，首先检查最内层作用域（按括号计），然后按顺序依次检查外部作用域。测试用例中每一个表达式都是合法的。有关作用域的更多详细信息，请参阅示例。

思路：



编码：

```java
```

### 2022.07.04

[**1200. 最小绝对差**](https://leetcode.cn/problems/minimum-absolute-difference/)

> 给你个整数数组 `arr`，其中每个元素都 **不相同**。
>
> 请你找到所有具有最小绝对差的元素对，并且按升序的顺序返回。

思路：

对 arr 进行升序排序，那么最小绝对差一定相邻，接下来进行比较，注意当遇到比当前小的时，主要清空之前的。

编码：

MinimumAbsDifference.java / Solution1200.java

```java
package cn.parulpan.code.questionoftheday;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

/**
 * 1200. 最小绝对差
 * https://leetcode.cn/problems/minimum-absolute-difference/
 * <p>
 * 数据结构: 数组
 * 算法: 排序
 *
 * @author chengyan
 * @since 2022/07/04
 */
public class Solution1200 {
    public static void main(String[] args) {
        System.out.println(new Solution1200().minimumAbsDifference(new int[]{4, 2, 1, 3}));
        System.out.println(new Solution1200().minimumAbsDifference(new int[]{1, 3, 6, 10, 15}));
        System.out.println(new Solution1200().minimumAbsDifference(new int[]{3, 8, -10, 23, 19, -4, -14, 27}));
    }

    public List<List<Integer>> minimumAbsDifference(int[] arr) {
        int length = arr.length;
        Arrays.sort(arr);

        int best = Integer.MAX_VALUE;
        List<List<Integer>> result = new ArrayList<>();
        for (int i = 0; i < length - 1; i++) {
            int temp = arr[i + 1] - arr[i];
            if (temp < best) {
                best = temp;
                result.clear();
                ArrayList<Integer> pair = new ArrayList<>();
                pair.add(arr[i]);
                pair.add(arr[i + 1]);
                result.add(pair);
            } else if (temp == best) {
                ArrayList<Integer> pair = new ArrayList<>();
                pair.add(arr[i]);
                pair.add(arr[i + 1]);
                result.add(pair);
            }
        }

        return result;
    }
}

```

### 2022.07.01

[**241. 为运算表达式设计优先级**](https://leetcode.cn/problems/different-ways-to-add-parentheses/)

> 给你一个由数字和运算符组成的字符串 expression ，按不同优先级组合数字和运算符，计算并返回所有可能组合的结果。你可以 按任意顺序 返回答案。
>
> 生成的测试用例满足其对应输出值符合 32 位整数范围，不同结果的数量不超过 10^4 。

思路：

可以看作是一种分治的变形，把大问题划分为左右两个子问题，然后不断通过后序遍历的方式进行求解，求解过程中如果存在之前计算的子问题，则从 memMap 进行存取。

编码：

DiffWaysToCompute.java / Solution21.java

```java
package cn.parulpan.code.questionoftheday;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;

/**
 * 241. 为运算表达式设计优先级
 * https://leetcode.cn/problems/different-ways-to-add-parentheses/
 *
 * data structure: 字符串
 * algorithm: 递归 动态规划 记忆化搜索
 *
 * @author parzulpan
 * @since 2022/07/01
 */
public class Solution241 {
    public static void main(String[] args) {
        System.out.println(new Solution241().diffWaysToCompute("2-1-1"));
        System.out.println(new Solution241().diffWaysToCompute("2*3-4*5"));
    }

    HashMap<String, List<Integer>> memMap = new HashMap<>();

    public List<Integer> diffWaysToCompute(String expression) {

        return dfs(expression);
    }

    public List<Integer> dfs(String str) {
        int num = parseInt(str);
        if (num >= 0) {
            return new ArrayList<>() {{
                add(num);
            }};
        }
        // mem
        if (memMap.containsKey(str)) {
            return memMap.get(str);
        }

        ArrayList<Integer> res = new ArrayList<>();
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            if (ch == '+' || ch == '-' || ch == '*') {
                List<Integer> left = dfs(str.substring(0, i));
                List<Integer> right = dfs(str.substring(i + 1));
                int temp = 0;
                for (int l : left) {
                    for (int r : right) {
                        switch (ch) {
                            case '+':
                                temp = l + r;
                                break;
                            case '-':
                                temp = l - r;
                                break;
                            case '*':
                                temp = l * r;
                                break;
                            default:
                        }
                        res.add(temp);
                    }
                }
            }
        }
        memMap.put(str, res);

        return res;
    }

    public int parseInt(String str) {
        for (int i = 0; i < str.length(); i++) {
            if (!Character.isDigit(str.charAt(i))) {
                return -1;
            }
        }

        return Integer.parseInt(str);
    }
}

```

### 2022.06.28

[**324. 摆动排序 II**](https://leetcode.cn/problems/wiggle-sort-ii/)

> 给你一个整数数组 nums，将它重新排列成 nums\[0] < nums\[1] > nums\[2] < nums\[3]... 的顺序。
>
> 你可以假设所有输入数组都可以得到满足题目要求的结果。

思路：

? 看麻了，我的建议是直接开摆！

编码：

WiggleSort.java / Solution324.java

```java
package cn.parulpan.code.questionoftheday;

import java.util.Arrays;

/**
 * 324. 摆动排序 II
 * https://leetcode.cn/problems/wiggle-sort-ii/
 * <p>
 * data structure: 数组
 * algorithm: 分治 快速选择 排序
 *
 * @author chengyan
 * @since 2022/06/28
 */
public class Solution324 {
    public static void main(String[] args) {
        int[] nums1 = {1, 5, 1, 1, 6, 4};
        System.out.println(Arrays.toString(nums1));
        new Solution324().wiggleSort(nums1);
        System.out.println(Arrays.toString(nums1));

        System.out.println();

        int[] nums2 = {1, 3, 2, 2, 3, 1};
        System.out.println(Arrays.toString(nums2));
        new Solution324().wiggleSort(nums2);
        System.out.println(Arrays.toString(nums2));
    }

    public void wiggleSort(int[] nums) {
        int[] arr = nums.clone();
        Arrays.sort(arr);
        int n = nums.length;
        int x = (n + 1) / 2;
        for (int i = 0, j = x - 1, k = n - 1; i < n; i += 2, j--, k--) {
            nums[i] = arr[j];
            if (i + 1 < n) {
                nums[i + 1] = arr[k];
            }
        }
    }
}

```

### 2022.06.27

[**522. 最长特殊序列 II**](https://leetcode.cn/problems/longest-uncommon-subsequence-ii/)

> 给定字符串列表 strs ，返回其中 最长的特殊序列 。如果最长特殊序列不存在，返回 -1 。
>
> 特殊序列 定义如下：该序列为某字符串 独有的子序列（即不能是其他字符串的子序列）。
>
> s 的 子序列可以通过删去字符串 s 中的某些字符实现。
>
> 例如，"abc" 是 "aebdc" 的子序列，因为您可以删除"aebdc"中的下划线字符来得到 "abc" 。"aebdc"的子序列还包括"aebdc"、 "aeb" 和 "" (空字符串)。

思路：



编码：

FindLUSLength.java / Solution522.java

```java
class Solution {
    public int findLUSlength(String[] strs) {

    }
}
```

### 2022.06.25

[**剑指 Offer II 091. 粉刷房子**](https://leetcode.cn/problems/JEj789/)

> 假如有一排房子，共 n 个，每个房子可以被粉刷成红色、蓝色或者绿色这三种颜色中的一种，你需要粉刷所有的房子并且使其相邻的两个房子颜色不能相同。
>
> 当然，因为市场上不同颜色油漆的价格不同，所以房子粉刷成不同颜色的花费成本也是不同的。每个房子粉刷成不同颜色的花费是以一个 n x 3 的正整数矩阵 costs 来表示的。
>
> 例如，costs\[0]\[0] 表示第 0 号房子粉刷成红色的成本花费；costs\[1]\[2] 表示第 1 号房子粉刷成绿色的花费，以此类推。
>
> 请计算出粉刷完所有房子最少的花费成本。

思路：



编码：

MinCost.java

```java
class Solution {
    public int minCost(int[][] costs) {

    }
}
```

### 2022.06.18

[**剑指 Offer II 029. 排序的循环链表**](https://leetcode.cn/problems/4ueAj6/)

> 给定循环单调非递减列表中的一个点，写一个函数向这个列表中插入一个新元素 insertVal ，使这个列表仍然是循环升序的。
>
> 给定的可以是这个列表中任意一个顶点的指针，并不一定是这个列表中最小元素的指针。
>
> 如果有多个满足条件的插入位置，可以选择任意一个位置插入新的值，插入后整个列表仍然保持有序。
>
> 如果列表为空（给定的节点是 null），需要创建一个循环有序列表并返回这个节点。否则。请返回原先给定的节点。

思路：



编码：

Insert.java

```java
class Solution {
    public Node insert(Node head, int insertVal) {
        
    }
}
```

### 2022.06.17

[**1089. 复写零**](https://leetcode.cn/problems/duplicate-zeros/)

> 给你一个长度固定的整数数组 arr，请你将该数组中出现的每个零都复写一遍，并将其余的元素向右平移。
>
> 注意：请不要在超过该数组长度的位置写入元素。
>
> 要求：请对输入的数组 就地 进行上述修改，不要从函数返回任何东西。

思路：



编码：

DuplicateZeros.java

```java
class Solution {
    public void duplicateZeros(int[] arr) {

    }
}
```





