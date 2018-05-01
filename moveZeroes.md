# Practice
移动零
## 问题分析：
#### 
给定一个数组 nums, 编写一个函数将所有 0 移动到它的末尾，同时保持非零元素的相对顺序。
## 编程实现：
```C
void moveZeroes(int* nums, int numsSize) {
    int i= 0;
    int sum= 0;
    for(i = 0;i < numsSize;i++) 
    {
        if(nums[i] != 0) 
        {
            nums[sum++]  = nums[i];
        }
    }
    while(sum<numsSize) {
        nums[sum++] = 0;
    }
}
```
## 总结体会：
本题先遍历数组，寻找出不为0的数提前，然后再利用循环将后面的数据置0，即实现了把0移动到数组后。