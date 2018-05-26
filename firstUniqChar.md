#题目
字符串中的第一个唯一字符
## 问题：
#### 
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。
## 编程实现：
```C++
class Solution {
public:
    int firstUniqChar(string s) {
       int n=s.size();  
        int a[26]={0};  
        for(int i=0;i<n;i++)  
            a[s[i]-'a']++;    
        for(int i=0;i<n;i++)  
        {  
            if(a[s[i]-'a']==1)  
                return i;  
        }  
        return -1;   
    }
};
```
##总结
首先定义一个数组，遍历数组计算每个字母的个数，然后返回第一个字母数为1的下标即可。