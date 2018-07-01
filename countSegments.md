#题目
字符串中的单词数
## 问题： 
统计字符串中的单词个数，这里的单词指的是连续的不是空格的字符。

请注意，你可以假定字符串里不包括任何不可打印的字符。
## 编程实现：
```C++
class Solution {
public:
    int countSegments(string s) {
       int n=s.size();
        if(n==0)
            return 0;
        int flag=0;
        int m=0;
        for(int i=0;i<n;i++)
        {
            if(s[i]!=' ')
            {
                flag=1;
            }
            if(flag)
                if(s[i]==' ')
                {
                    m++;
                    flag=0;
                }
        }
        if(flag)
            m++;
        return m; 
    }
};
```
##总结
首先判断第一个字符，如果第一个字符为空格，则不计数，直到遇到第一个不为空格的字符开始计数。然后再找空字符，找到后再计数，连续的字符串不计数。如果最后一个字符不是空也会计数。