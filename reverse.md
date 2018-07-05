#题目
反转整数
## 问题： 
给定一个 32 位有符号整数，将整数中的数字进行反转。
## 编程实现：
```C++
class Solution {
public:
    int reverse(int x) {
         const int int_max=0x7fffffff;
        const int int_min=0x80000000;
        long long anwser=0;
        while(x!=0)
        {
            anwser=anwser*10+(x%10);
            x/=10;
        }
        if(anwser<int_min || anwser>int_max)
        {
            anwser=0;
        }
        return anwser;
    }
};
```
##总结
本题利用while循环，每次取出低位，然后乘10不断地将低位乘到高位，循环结束即可。