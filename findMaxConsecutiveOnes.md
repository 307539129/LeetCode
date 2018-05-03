# 题目
最大连续1的个数
## 问题：
#### 
给定一个二进制数组， 计算其中最大连续1的个数。
## 编程实现：
```C
int findMaxConsecutiveOnes(int* nums, int numsSize) {
  int number=0,maxnumber=0,i=0;
    for(;i<numsSize;i++)
    { while(nums[i]==1&&i<numsSize)
        { 
          i++; 
          number++;
        }
         if(number>maxnumber)
            maxnumber=number;
            number=0;
     }
    return maxnumber;
}
```
## 总结体会：
本题通过遍历数组，用while循环判断连续1个数，多次统计后跟当前最大值比较，数组遍历完成后即可求出最大值。