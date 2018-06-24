#题目
反转字符串 II
## 问题： 
给定一个字符串和一个整数 k，你需要对从字符串开头算起的每个 2k 个字符的前k个字符进行反转。如果剩余少于 k 个字符，则将剩余的所有全部反转。如果有小于 2k 但大于或等于 k 个字符，则反转前 k 个字符，并将剩余的字符保持原样。
## 编程实现：
```C++
class Solution {
public:
    string reverseStr(string s, int k) {
      int n = s.size();
        int x = 0;
        for(int i=0;i<n;)
        {
            if(n-i>=k)
                x=k;
            else if(n-i<k)
                x=n-i;
            reverse(s.begin()+i,s.begin()+i+x);
            if(n-i>2*k)
                i+=2*k;
            else
                return s;
        }
        return s;  
    }
};
```
##总结
本题采用了reverse函数，分两种情况进行翻转，如果字符串长度小于k或等于k，用函数全部翻转，再判断是否到了2k，超出2k的部分再进行按照同样的规则翻转。