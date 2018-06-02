#题目
三个数的最大乘积
## 问题：
#### 
给定一个整型数组，在数组中找出由三个数组成的最大乘积，并输出这个乘积。
## 编程实现：
```C++
class Solution {
public:
    int maximumProduct(vector<int>& nums) {
      int n = nums.size();
        sort(nums.begin(), nums.end());
        int p = nums[0] * nums[1] * nums[n - 1];
        return max(p, nums[n - 1] * nums[n - 2] * nums[n - 3]);
    }
};
```
##总结
首先对数组排序，考虑数值为正还是为负。如果最大值为负值，则数组中所有的值都为负值，最大的乘积就是最后三位数字的乘积；如果最大值为正值，则数组中可能存在负值，若都为正值，最大乘积为最后三位的乘积，若存在负值，可能最大值为最大数与前两位的乘积，因此只需判断最后三位的乘积以及最后一个数与前两位的乘积即可。