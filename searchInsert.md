#题目
搜索插入位置
## 问题：
#### 
给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。
## 编程实现：
```C++
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        if( nums.size() == 0)
              return 0;
          int left = 0,right = nums.size() - 1;
          while(left <= right)
          {
              int mid = (left+right) / 2;
              if( nums[mid] == target)
                 return mid;
             else if( nums[mid] > target)
                 right = mid -1;
             else
                 left = mid + 1 ;
        }
         return right+1;
    }
};
```
##总结
如果数组为空就直接返回，数组不为空时，采用二分法查找，如果该数在数组中，则返回下标。如果不在数组中，则返回当前下标+1，如果大于最大值则在最后位置插入。 