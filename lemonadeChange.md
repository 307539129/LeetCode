#题目
柠檬水找零
## 问题： 
在柠檬水摊上，每一杯柠檬水的售价为 5 美元。

顾客排队购买你的产品，（按账单 bills 支付的顺序）一次购买一杯。

每位顾客只买一杯柠檬水，然后向你付 5 美元、10 美元或 20 美元。你必须给每个顾客正确找零，也就是说净交易是每位顾客向你支付 5 美元。

注意，一开始你手头没有任何零钱。

如果你能给每位顾客正确找零，返回 true ，否则返回 false 。
## 编程实现：
```C++
class Solution {
public:
    bool lemonadeChange(vector<int>& bills) {
        int bills_5 = 0;
        int bills_10 = 0;
        int bills_20 = 0;
        for(int i=0;i<bills.size();i++)
        {
            int now_buy = bills[i];
            if(now_buy==5)
            {
                bills_5++;
            }
            else if(now_buy == 10)
            {
                if(bills_5==0)
                    return false;
                else bills_5--;
                bills_10++;
            }
            else
            {
                if(bills_10==0)
                {
                    if(bills_5<=2)
                        return false;
                    else
                    {bills_5-=3;continue;}
                }
                else
                {
                    if(bills_5==0)
                        return false;
                    else
                    {bills_5--;bills_10--;continue;}
                }
                bills_20++;
            }
        }
        return true;
    }
};
```
##总结
遍历数组并且记录目前有的钞票数，如果来的人给了5元，直接通过，5元钞票数加1，如果来的人给了10元，只要至少还有一张5元的，就通过，如果给了20元，优先把10元的钞票退出去，然后退5元的，如果不能退就失败。