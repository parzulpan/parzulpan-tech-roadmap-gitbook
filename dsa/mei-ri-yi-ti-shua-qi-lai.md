# 每日一题刷起来

[LeetCode](https://leetcode.cn/u/parzulpan/)，这玩意就像做数学题似的，在掌握基础知识和一些解题模板之后，刷就完事了\~ :tada:



### 2022.07.01

[**241. 为运算表达式设计优先级**](https://leetcode.cn/problems/different-ways-to-add-parentheses/)

> 给你一个由数字和运算符组成的字符串 expression ，按不同优先级组合数字和运算符，计算并返回所有可能组合的结果。你可以 按任意顺序 返回答案。
>
> 生成的测试用例满足其对应输出值符合 32 位整数范围，不同结果的数量不超过 10^4 。

思路：



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



编码：

WiggleSort.java

```java
class Solution {
    public void wiggleSort(int[] nums) {
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

FindLUSlength.java

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





