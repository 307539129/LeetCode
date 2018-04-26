# Practice
求众数
## 问题分析：
#### 
给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。
假设数组是非空的，并且给定的数组总是存在众数。
## 编程实现：
```C++
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int i=0;
        int j=0;
        float sum=0;
        int n=sizeof(nums)/sizeof(nums[0]);
        float q=n/2;
        for( i=0;i<=n;i++)
        {  for( j=0;j<=n;j++)
              if(nums[i]==nums[j])
                    sum++;
             if(sum>q)
                 return nums[i-1];
        }   
    }
};
```
## 总结体会：
首先把数组元素从第一个开始跟数组其他元素进行比较，求出相同的次数再判断跟n/2的关系，找出众数。