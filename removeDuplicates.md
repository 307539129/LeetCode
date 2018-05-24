#题目
删除排序数组中的重复项
## 问题：
#### 
给定一个排序数组，你需要在原地删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。
不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。
## 编程实现：
```C++
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
      int count=0;
        for(int i=1;i<nums.size();i++)
        {
            if(nums[i]==nums[i-1])
                count++;
            else
                nums[i-count]=nums[i];
        }
        return nums.size()-count;  
    }
};
```
##总结
用count来计算相同的数据，重复一次count+1，当遇到不重复的数据的时候，将数据放到第一次重复的位置，将重复的数据覆盖，循环结束后返回原数组长度减去重复的次数即可。