# Practice
汉明距离
## 问题分析：
#### 
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。
给出两个整数 x 和 y，计算它们之间的汉明距离。
## 编程实现：
```C++
class Solution {
public:
    int hammingDistance(int x, int y) {
        int xora;
        xora=x^y;
        int sum=0;
         while(xora!=0)
        {
            if(xora&1==1)
            {
                sum++;
            }
            xora=xora>>1;
        }
        return sum;
    }
};
```
## 总结体会：
本题先求两数的异或，然后取出最低位与1比较，如果最低位为1，则有一位不同，再移位后比较，求出不同的位数。