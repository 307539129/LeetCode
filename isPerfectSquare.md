#题目
有效的完全平方数
## 问题：
#### 
给定一个正整数 num，编写一个函数，如果 num 是一个完全平方数，则返回 True，否则返回 False。
## 编程实现：
```C++
class Solution {
public:
    bool isPerfectSquare(int num) {
        int i = 1;
        while (num > 0) {
            num -= i;
            i += 2;
        }
        return num == 0; 
    }
};
```
##总结
完全平方数为一系列奇数的和，利用while循环判断num能否分解成奇数，如果可以分解，num就为完全平方数。