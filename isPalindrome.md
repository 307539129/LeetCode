#题目
回文数
## 问题：
#### 
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。
## 编程实现：
```C++
class Solution {
public:
    bool isPalindrome(int x) {
     if (x == 0) return true;
    if (x < 0 || x % 10 == 0)
        return false;
    int y = 0;
    while (y < x) {
        y = y * 10 + (x % 10);
        if (x == y)  
            return true;
        x /= 10;
    }
    return x == y;    
    }
};
```
## 总结体会：
首先排除负数和个位为0的数，利用循环取出数的每个位，先取出低位然后把低位逐渐变成高位，循环结束后判断是否相等。