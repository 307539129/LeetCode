#题目
4的幂
## 问题：
#### 
给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂。
## 编程实现：
```C++
class Solution {
public:
    bool isPowerOfFour(int num) {
       int mod = 0;  
   while(mod ==0 && num>= 4){  
       mod = num %4;  
       num = num/4;  
   }  
   if(mod != 0){  
       return false;  
   }  
   if(num == 1){  
       return true;  
   }  
   return false;   
    }
};
```
##总结
用输入的数除以4，多次除后如果能得到余数为0，则该数是4的幂，否则不是。