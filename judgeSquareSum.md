#题目
平方数之和
## 问题：
#### 
给定一个非负整数 c ，你要判断是否存在两个整数 a 和 b，使得 a2 + b2 = c。
## 编程实现：
```C++
class Solution {
public:
    bool judgeSquareSum(int c) {
        int i = 0;
        int j = sqrt(c);
        while (i <= j) 
        {
            if (i*i + j*j== c) 
                return true;
            else if (i*i+j*j< c)
                i++;
            else j--;
        }
        return false;
    }
};
```
##总结
分别从0和c的平方根开始循环，通过while循环遍历，如果i*i+j*j等于c，那么返回true；如果i*i+j*j小于c，则j增大1,如果i*i+j*j大于c，则j减1，如果循环结束没有找到则返回false。