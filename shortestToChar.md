#题目
字符的最短距离
## 问题： 
给定一个字符串 S 和一个字符 C。返回一个代表字符串 S 中每个字符到字符串 S 中的字符 C 的最短距离的数组。
## 编程实现：
```C++
class Solution {
public:
    vector<int> shortestToChar(string S, char C) {
        int n=S.size();  
        vector<int> ans(n,n); 
        for(int i=0;i<n;i++)  
            if(S[i]==C) 
                ans[i]=0;  
        for(int i=1;i<n;i++) 
            ans[i]=min(ans[i],ans[i-1]+1);  
        for(int i=n-2;i>=0;--i) 
            ans[i]=min(ans[i],ans[i+1]+1);  
        return ans;  
    }
};
```
##总结
首先设置一个初始值都是n的向量，找到字符C的位置，设置数组值为0，分别从左右两侧遍历数组，找出最短距离。