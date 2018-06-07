#题目
旋转字符串
## 问题： 
给定两个字符串, A 和 B。
A 的旋转操作就是将 A 最左边的字符移动到最右边。 例如, 若 A = 'abcde'，在移动一次之后结果就是'bcdea' 。如果在若干次旋转操作之后，A 能变成B，那么返回True。
## 编程实现：
```C++
class Solution {
public:
    bool rotateString(string A, string B) {
         int i=0,j=0,s1=A.size(),s2=B.size();
    if(s1!=s2)
        return false;
    if(s1==0)
        return true;
    bool flag;
    while(j<s1)
    {
        while(j<s1)
        {
            if(B[0]==A[j])
                break;
            j++;
        }
        flag=1;
        i=0;
        int t1=1,t2=j+1;
        while(t2<s1)
        {
            if(B[t1]!=A[t2])
            {
                flag=0;
                break;
            }
            t1++;
            t2++;
        }
        if(flag==1)
        {
            while(t1<s1)
            {
                if(B[t1]!=A[i])
                {
                    flag=0;
                    break;
                }
                t1++;
                i++;
            }
        }
        if(flag==1)
            return true;
        j++;
    }
    return false;
    }
};
```
##总结
先判断B的首字母在A中的位置，然后对数组进行判断是否匹配，然后再比较A中前半部分是否与B中剩余部分相等，当前半部分和后半部分匹配结束后证明数组可以旋转后相等。