#题目
最长连续递增序列
## 问题：
#### 
给定一个未经排序的整数数组，找到最长且连续的的递增序列。
## 编程实现：
```C
int findLengthOfLCIS(int* nums, int numsSize) {
    int i,number=1,mnumber=1;
    if(numsSize==0)
        return 0;
        else
        {
    for(i=0;i<numsSize-1;i++)
        if(nums[i]<nums[i+1])
          number++;
        else 
        {if(mnumber<number)
             mnumber=number;
           number=1;
        }
     if(mnumber<number)
            mnumber=number;       
    return mnumber;}
}
```
## 总结体会：
本题先判断数组是否为0，不为0的情况下再判断相邻两个数的大小，如果始终前一个数比后一个小，计数+1，当不满足前一个数小后，重新开始计数，同时保存当前计数值，求出最大值后返回即可。