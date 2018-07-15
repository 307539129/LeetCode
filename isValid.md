#题目
有效的括号
## 问题： 
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。

有效字符串需满足：

1.左括号必须用相同类型的右括号闭合。
2.左括号必须以正确的顺序闭合。
注意空字符串可被认为是有效字符串。
## 编程实现：
```C++
class Solution {
public:
    bool isValid(string s) {
        int j = 0;
	string temp;
	int len = s.size();
	temp += s[0];
 
	if (s[0] == '(' || s[0] == '[' || s[0] == '{')
    {
		for (int i = 1;i < len;i++)
        {
			if ((s[i] == temp[j] + 1) || (s[i] == temp[j] + 2))
            {
				temp.erase (temp.end()-1);
				j--;
			}
			else 
            {
				temp += s[i];
				j++;
			}
		}
		if (temp.empty())
			return true;
		else return false;		
	}
	else{
	if (s  == "")
		return true;
	else return false;
	}
    }
};
```
##总结
定义一个新的string，将原string的内容存储进新的string中。每读入一个新的字符就与前一个字符比较，看是否相差1或2。如果相差1或2就看做配对成功，把最新读入的和它前一个字符一起消掉，如果不匹配就入栈。读入完毕后，看新定义的string是否为空，如果为空说明全部配对成功，返回true，否则返回false。