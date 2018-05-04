# 题目
3的幂
## 问题：
#### 
给出一个整数，写一个函数来确定这个数是不是3的一个幂。
## 编程实现：
```C++
class Solution {
public:
    bool isPowerOfThree(int n) {
    if(n==1)
         return true;
        if(n==0)
            return false;
        if(n==2)
            return false;
        while(n%3==0)
     {  
         n=n/3;
            if(n==1)
         return true;
     }
       return false; 
    }
};
```
## 总结体会：
首先判断0,1,2，再利用循环除3运算，当多次被3除后变为1即为3的幂，否则不是。