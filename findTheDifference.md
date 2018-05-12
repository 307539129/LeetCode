#题目
找不同
## 问题：
#### 
给定两个字符串 s 和 t，它们只包含小写字母。
字符串 t 由字符串 s 随机重排，然后在随机位置添加一个字母。
请找出在 t 中被添加的字母。
## 编程实现：
```C++
class Solution {
public:
    char findTheDifference(string s, string t) {
        char result=s[0];
        for(int i=1;i<s.length();i++){
            result^=s[i];
        }
        for(int i=0;i<t.length();i++){
            result^=t[i];
        }
        return result;
    }
};
```
##总结
每次加入一个字母，两个字符的ASCII码异或为0，0与任何数异或为数本身，将两个字符串的所有字符的ASCII码进行异或运算，最终得到的是新增的字符。