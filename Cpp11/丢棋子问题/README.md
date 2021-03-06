# 丢棋子问题

[提交链接](https://www.nowcoder.com/practice/d1418aaa147a4cb394c3c3efc4302266?tpId=117&&tqId=35279&rp=1&ru=/ta/job-code-high&qru=/ta/job-code-high/question-ranking)

## 思路

- 如果棋子数多于二分查找的次数，就直接二分查找
- 否则考虑 $f_{i, j}$ 表示用 $i$ 个棋子，扔 $j$ 次最多能够解决的楼层数。
    - 然后考虑将第 $i$ 个棋子扔在 $a$ 楼层是最优的尝试：
        - 如果这个棋子碎了，那么向下，就是 $i - 1$ 个棋子扔 $j - 1$ 次能搞定多少层，即 $f_{i - 1, j - 1}$。
        - 如果这个棋子没碎，那么向上，就是 $i - 1$ 个棋子扔 $j$ 次能搞定多少层，即 $f_{i - 1, j}$。
        - $a$ 这一层本身也被搞定了。
      - 所以有 $f_{i, j} = f_{i - 1, j} + f_{i - 1, j - 1} + 1$。
