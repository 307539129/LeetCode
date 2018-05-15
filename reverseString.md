#题目
反转字符串
## 问题：
#### 
请编写一个函数，其功能是将输入的字符串反转过来
## 编程实现：
```C++
class Solution {
public:
    string reverseString(string s) {
      int left = 0, right = s.size() - 1;
        while (left < right) 
        {
            char t = s[left];
            s[left++] = s[right];
            s[right--] = t;
        }
        return s;
    }
};
```
##总结
从两侧分别遍历字符串，交换两侧字符，当left不再小于right的时候，数组就交换完成，返回数组即可。