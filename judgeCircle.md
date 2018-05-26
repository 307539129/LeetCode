#题目
判断路线成圈
## 问题：
#### 
初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一个圆圈，换言之就是判断它是否会移回到原来的位置。
移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。
## 编程实现：
```C++
class Solution {
public:
    bool judgeCircle(string moves) {
      int x = 0,y = 0;
        for (int i=0;i<moves.size();i++)
        {
            if (moves[i] == 'U') y++;
            if (moves[i] == 'D') y--;
            if (moves[i] == 'R') x++;
            if (moves[i] == 'L') x--;
        }
        if (x == 0 && y == 0)
            return true;
        else
            return false;  
    }
};
```
##总结
用（x，y）来表示当前坐标 ，每次向上则是y+1 向下则是y-1 向右是x+1 向左是x-1 
遍历字符串，如果最终位置是（0,0），就说明形成了圈。