#题目
移除元素
## 问题：
#### 
给定一个数组 nums 和一个值 val，你需要原地移除所有数值等于 val 的元素，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。

元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。
## 编程实现：
```C++
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
       if(nums.size() == 0) 
           return 0;  
        int j = 0;  
        for(int i = 0;i < nums.size();++i)
        {  
            if(nums[i] == val) 
                continue;  
            nums[j++] = nums[i];  
        }  
        return j;   
    }
};
```
## 总结体会：
首先判断数组是否为空，不为空的情况下遍历数组，把不等于val的数重新复制到数组中，当遍历结束后，等于val的数将被覆盖。