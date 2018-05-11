#题目
宝石与石头
## 问题：
#### 
 给定字符串J 代表石头中宝石的类型，和字符串 S代表你拥有的石头。 S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。

J 中的字母不重复，J 和 S中的所有字符都是字母。字母区分大小写，因此"a"和"A"是不同类型的石头。
## 编程实现：
```C++
class Solution {
public:
    int numJewelsInStones(string J, string S)
    {
          int sum = 0;
        for(int j=0; j<J.length(); j++)         
            for(int s=0; s<S.length(); s++) 
                if(J[j] == S[s]) 
                    sum++;
        return sum;  
    }
};
```
##总结
通过两个for循环遍历两个字符串，判断给定字符串的类型与你拥有的宝石类型，如果相同则计数一次，最后返回计数值。