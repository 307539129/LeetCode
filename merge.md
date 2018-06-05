#题目
合并两个有序数组
## 问题：
#### 
给定两个有序整数数组 nums1 和 nums2，将 nums2 合并到 nums1 中，使得 num1 成为一个有序数组。
## 编程实现：
```C++
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int end=m+n-1;
        m--;
        n--;
        while(m>=0&&n>=0)
            if(nums2[n]>nums1[m])
                nums1[end--]=nums2[n--];
            else
                nums1[end--]=nums1[m--];
        while(n>=0)
            nums1[end--]=nums2[n--];
    }
};
```
##总结
先算出数组的元素数，判断两个数组的最大值哪个更大，更大的放到新数组的最后，当其中一个数组遍历结束后，再将另外一个数组插入到数组前即可。