#题目
求众数
## 问题：
#### 
给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。
你可以假设数组是非空的，并且给定的数组总是存在众数。
## 编程实现：
```C++
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int res = 0;  
        int num = 0;  
        for (int i = 0; i < nums.size(); i++) {  
            if ( num== 0) 
            {  
                res = nums[i];  
                num++;  
            }  
            else{ 
                if(nums[i] == res) 
                    num++; 
                    else num--;
                }  
        }  
        return res;  
    }
};
```
##总结
通过for循环遍历，先假设第一个就是res，如果后面有与res相等的就计数，如果不相等就减一，最后循环结束后num不为0时对应的数就是众数，返回res即可。