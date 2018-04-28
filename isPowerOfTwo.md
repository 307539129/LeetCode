# Practice
 2的幂
## 问题分析：
#### 
给定一个整数，写一个函数来判断它是否是2的幂。
## 编程实现：
```C++
class Solution {
public:
    bool isPowerOfTwo(int n) {
        if(n==1)
         return true;
        if(n==0)
            return false;
        while(n%2==0)
     {  
         n=n/2;
            if(n==1)
         return true;
     }
       return false; 
    }
};
```
## 总结体会：
本题用2除n，判断余数，如果余数为0，则n直接除以2再替换为n，当n变为1时，即n为2的幂。当除到n%2不为0时，n不是2的幂。程序开始后0和1不适用循环，在开始循环前单独判断。