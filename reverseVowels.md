#题目
反转字符串中的元音字母
## 问题： 
编写一个函数，以字符串作为输入，反转该字符串中的元音字母。
## 编程实现：
```C++
class Solution {
public:
    string reverseVowels(string s) {
        int left = 0, right= s.size() - 1;
        while (left < right) 
        {
            if (isVowel(s[left]) && isVowel(s[right])) 
                swap(s[left++], s[right--]);
             else if (isVowel(s[left])) 
                --right;
                else 
                ++left;
        }
        return s;
    }
    bool isVowel(char c)
    {
        return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' || c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U';
    }
};
```
##总结
翻转字符串中的元音字母，通过isVowel的函数来判断当前字符是否为元音字母，如果两边都是元音字母，那么我们交换，如果左边的不是，向右移动一位，如果右边的不是，则向左移动一位。