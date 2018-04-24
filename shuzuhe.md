# Practice
两数之和
## 问题分析：
#### 
给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。
你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。
## 编程实现：
```C++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) 
    {
       int i,j;
        vector<int> a;
        for(i=0;i<sizeof(nums)/sizeof(nums[0]);++i)
            for(j=i+1;j<sizeof(nums)/sizeof(nums[0]);++j)
                if(nums[i]+nums[j]==target)
                {
                    a.push_back(i);
                    a.push_back(j);
                    return a;
                }   
    }
};
```
## 总结体会：
本题使用两个for循环进行遍历数组，找到符合要求的数后立即返回数组的下标。