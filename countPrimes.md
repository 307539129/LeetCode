#题目
计数质数
## 问题：
#### 
统计所有小于非负数整数 n 的质数的数量。
## 编程实现：
```C++
class Solution {
public:
   int countPrimes(int n) {
        int count = 0;
   for (int i = 1; i < n; i++) 
      if (isPrime(i)) 
          count++;
   return count;
}
 bool isPrime(int num) {
   if (num <= 1)
       return false;
   for (int i = 2; i * i <= num; i++) 
      if (num % i == 0) 
          return false;
   return true;
    }
};
```
##总结
首先用isPrime函数判断一个数是不是质数，再通过for循环进行调用isPrime判断小于n的所有数，如果是质数count+1，循环结束即可求出小于n的所有质数的个数。