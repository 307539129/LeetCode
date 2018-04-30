# Practice
缺失数字
## 问题分析：
#### 
给出一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。
## 编程实现：
```C
int missingNumber(int* nums, int numsSize) 
{
    int sum=0;
    int sumn=(numsSize+1)*numsSize/2;
    for(int i=0;i<numsSize;i++)
        sum+=nums[i];
    return sumn-sum;
}
```
## 总结体会：
本题先求出n个数的和，然后求出数组里所有数的和，再相减，即可得出缺失的数。