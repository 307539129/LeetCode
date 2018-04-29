# Practice
数字的补数
## 问题分析：
#### 
给定一个正整数，输出它的补数。补数是对该数的二进制表示取反。
## 编程实现：
```C++
class Solution {
public:
    int findComplement(int num) 
    {
          unsigned mask =~0;  
        while (num & mask) 
            mask <<= 1;  
        return ~mask & ~num;  
    }  
};
```
## 总结体会：
本题用到了数的掩码，先用全1数与数据相与，不断地移位，当mask数据与num相与为0时，mask即为掩码，掩码取反后再与数据取反相与，就可以数据取反后前面的1变为0.