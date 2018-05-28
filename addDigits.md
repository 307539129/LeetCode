#题目
各位相加
## 问题：
#### 
给定一个非负整数 num，反复将各个位上的数字相加，直到结果为一位数。
## 编程实现：
```C++
class Solution {
public:
    int addDigits(int num) {
       int sum=0,bit=0,n=num;
        if (num == 0) 
            return 0;
        while (n != 0)
        {
            sum += n%10;
            n/=10;
            bit++;
        }
        if (bit == 1) 
            return num;
        else 
            return addDigits(sum); 
    }
};
```
##总结
本题采用递归方式，不断地取出个位数并将数相加，当循环到只有一位数时不再进行调用函数，直接返回该数。