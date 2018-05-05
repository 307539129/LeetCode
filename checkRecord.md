# 题目
学生出勤纪录 I
## 问题：
#### 
给定一个字符串来代表一个学生的出勤纪录，这个纪录仅包含以下三个字符：

'A' : Absent，缺勤
'L' : Late，迟到
'P' : Present，到场
如果一个学生的出勤纪录中不超过一个'A'(缺勤)并且不超过两个连续的'L'(迟到),那么这个学生会被奖赏。

你需要根据这个学生的出勤纪录判断他是否会被奖赏。
## 编程实现：
```C
bool checkRecord(char* s) {
    int i=0,a=0,l=0;
    while(s[i]!='\0')
    {   if(s[i]=='A')
     a++;
            if(s[i]=='L')
            { l++;
                if(l>2)
                    return false;
            }
               else l=0;
     i++;
    }
  if(a<=1)
      return true;
    else 
        return false;
}
```
## 总结体会：
遍历字符串数组，当等于A时计数，在循环内判断L是否符合要求，如果不符合要求直接返回false，再循环外判断A的数量，符合要求就返回true。