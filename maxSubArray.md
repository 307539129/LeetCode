#题目
最大子序和
## 问题：
#### 
给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。
## 编程实现：
```C++
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
       int sum = nums[0];
            int cur = nums[0];
            if(nums.size() == 0)
                return nums[0];
            for(int i=1;i<nums.size();i++)
            {
                if(cur < 0)
                    cur = 0;
                cur = cur + nums[i];
                if(sum <= cur)
                    sum = cur;
            }
            return sum;  
    }
};
```
##总结
先假设第一个数为最大的和即为cur，判断是否小于0，如果小于0就将cur置0，遍历数组，排除负数，把正数加到cur中，每次循环都更新sum的值，当for循环结束后就求出了最大子序和。