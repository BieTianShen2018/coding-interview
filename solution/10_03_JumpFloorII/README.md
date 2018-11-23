## 变态跳台阶

### 题目描述
一只青蛙一次可以跳上`1`级台阶，也可以跳上`2`级……它也可以跳上`n`级。求该青蛙跳上一个`n`级的台阶总共有多少种跳法。

### 解法
跳上 `n-1` 级台阶，可以从 `n-2` 级跳 `1` 级上去，也可以从 `n-3` 级跳 `2` 级上去...也可以从 `0` 级跳上去。那么
```
f(n-1) = f(0) + f(1) + ... + f(n-2) ①
```

跳上 `n` 级台阶，可以从 `n-1` 级跳 `1` 级上去，也可以从 `n-2` 级跳 `2` 级上去...也可以从 `0` 级跳上去。那么
```
f(n) = f(0) + f(1) + ... + f(n-2) + f(n-1)  ②

②-①：
f(n) - f(n-1) = f(n-1)
f(n) = 2f(n-1)
```

所以 f(n) 是一个等比数列：
```
f(n) = 2^(n-1)
```


```java
/**
 * @author bingo
 * @since 2018/11/23
 */

public class Solution {
    /**
     * 青蛙跳台阶II
     * @param target 跳上的那一级台阶
     * @return 多少种跳法
     */
    public int JumpFloorII(int target) {
        return (int) Math.pow(2, target - 1);
    }
}
```

### 测试用例
1. 功能测试（如输入 3、5、10 等）；
2. 边界值测试（如输入 0、1、2）；
3. 性能测试（输入较大的数字，如 40、50、100 等）。