#题目
旋转数组
## 问题：
#### 
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。
## 编程实现：
```C++
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
      int len = nums.size();
        while (k > 0) {
            int cache = nums[len - 1];
            for (int x = len - 2; x >= 0; x--) 
                nums[x + 1] = nums[x];
            nums[0] = cache;
            --k;
        }  
    }
};
```
##总结
首先保存数组最后一个数，再通过for循环把数组元素后移，每次移位一个，移位一次k减1，当k到0时移位结束。