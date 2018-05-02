# Practice
只出现一次的数字
## 问题分析：
#### 
给定一个非空整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。
## 编程实现：
```C
int singleNumber(int* nums, int numsSize) {
   int result = 0;  
    for(int i=0; i < numsSize; i++)  
    {  
        result ^= nums[i];  
    }  
    return result;  
}
```
## 总结体会：
本题通过通过0与所有数据异或，利用异或运算具有交换律，两个相同的数据异或为0，转化为只出现1次的数据与0异或，结果为单个数本身，返回异或后的值即可。