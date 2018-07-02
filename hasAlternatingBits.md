#题目
交替位二进制数
## 问题： 
给定一个正整数，检查他是否为交替位二进制数：换句话说，就是他的二进制数相邻的两个位数永不相等。
## 编程实现：
```C++
class Solution {
public:
    bool hasAlternatingBits(int n) {
        int bit = -1;
        while (n > 0) {
            if (n & 1 == 1) 
            {
                if (bit == 1) 
                    return false;
                bit = 1;
            } else 
            {
                if (bit == 0) 
                    return false;
                bit = 0;
            }
            n >>= 1;
        }
        return true;
    }
};
```
##总结
本题一位一位来检测，用个变量bit来记录上一个位置的值，然后将数跟1与来获取最低位的值，如果是1，那么当此时bit已经是1的话，说明两个1相邻了，返回false，否则bit赋值为1。如果是0，那么当此时bit已经是0的话，说明两个0相邻了，返回false，否则bit赋值为0。判断完一次后将n向右移动一位。如果while循环退出了，说明01交替出现，返回true。