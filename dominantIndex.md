#题目
至少是其他数字两倍的最大数
## 问题： 
在一个给定的数组nums中，总是存在一个最大元素 。
查找数组中的最大元素是否至少是数组中每个其他数字的两倍。
如果是，则返回最大元素的索引，否则返回-1。
## 编程实现：
```C++
class Solution {
public:
    int dominantIndex(vector<int>& nums) {
        int mx = INT_MIN, secondMx = INT_MIN, mxId = 0;
        for (int i = 0; i < nums.size(); ++i) {
            if (nums[i] > mx) {
                secondMx = mx;
                mx = nums[i];
                mxId = i;
            } else if (nums[i] > secondMx) {
                secondMx = nums[i];
            }
        }
        if(mx - secondMx >= secondMx)
        return mxId ;
        else return -1;
    }
};
```
##总结
遍历数组分别求出最大数字和第二大数字，然后判断一下最大数字是否是第二大数字的两倍即可，最大值减去第二大的值，如果大于第二大的值就说明数组中元素至少是其他元素的两倍。