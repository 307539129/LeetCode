#题目
x 的平方根
## 问题： 
实现 int sqrt(int x) 函数。

计算并返回 x 的平方根，其中 x 是非负整数。

由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。
## 编程实现：
```C++
class Solution {
public:
    int mySqrt(int x) {
       if (x <= 1) 
           return x;
        int left = 0, right = x;
        while (left < right) 
        {
            int mid = left + (right - left) / 2;
            if (x / mid >= mid)
                left = mid + 1;
            else 
                right = mid;
        }
        return right - 1;
    }
};
```
##总结
本题采用二分法查找，查找求得的值的平方跟x的比较，找到一个不小于目标值的数。