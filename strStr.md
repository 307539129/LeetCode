#题目
实现strStr()
## 问题： 
实现 strStr() 函数。

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
## 编程实现：
```C++
class Solution {
public:
    int strStr(string haystack, string needle) {
      if(needle.size()==0)
            return 0;
        int length=haystack.length();
        int length_s=needle.length();
        int i,j;
        if(length<length_s)
            return -1;
        for(i=0;i<=length-length_s;++i)
        {
            if(haystack[i]==needle[0])
            {
                for(j=1;j<length_s;++j)
                {
                    if(haystack[i+j]==needle[j])
                        continue;
                    else
                        break;
                }
                if(j==length_s)
                    return i;
            }
        }
        return -1;
    }
};
```
##总结
本题先判断两个字符串长度，如果haystack长度小于needle长度，则直接返回-1，否则，从第一个字符串开始比较，匹配完成后返回匹配的起点，如果找不到匹配的长度，则代表匹配失败，返回-1。