C+API小游戏实验报告
==================
写得不够简洁，图片路径请自行更改，此为备份用<br>
一开始决定写清版动作类游戏是因为大家差不多都选完了，不想选重复的XD。<br>
玩了几天的小游戏还有横版网游之后才了解什么叫清版动作游戏（像DNF那样），后来发现人物要动作的话需要好多素材，根本找不到一整套… 于是上网扒了扒gif，之后就决定是你了——突击兵。<br>
决定了人物之后就在找怪物的gif素材，没有方向的找实在是太浪费时间了，而且还得把gif切分一下再加上相同的底色（为了用TransparentBlt这个函数）。图片、logo、鼠标光标、音乐，游戏基本素材整得比较久，毕竟都是自己ps弄的图，还有喜欢的动漫音乐，最后游戏做出来了倒是很欣慰的。<br>
<br>*运行截图*<br><br>
![relation](https://github.com/jckling/C-Game/blob/master/Report%20Images/1.png)
<br><br>
![relation](https://github.com/jckling/C-Game/blob/master/Report%20Images/2.png)  


<br><br>游戏设计
----------------------
游戏模块：人物、怪物、操作、等级、主函数<br>
1.人物：基本设定，动作图片载入与绘制，移动，状态判断<br>
2.怪物：属性设定、图片加载、动画绘制<br>
3.操作：怪物的移动、攻击，玩家的攻击、大招。距离判断函数<br>
4.等级：生成怪物，设定了各个关卡的怪物种类和数量<br>
5.主函数：音乐、过渡效果、菜单、游戏初始化、游戏进程。其他的还有基本的窗口创建、回调函数、响应键盘等<br>
	

<br><br>编程思路
----------------------
![relation](https://github.com/jckling/C-Game/blob/master/Report%20Images/20170726.png)  


<br><br>编程方案
----------------------
* 玩家：通过上下左右移动，X键攻击
	* 这里需要响应键盘和相应的绘图，以及攻击是否成功、玩家生命和能量的变化
* 怪物：Y轴追踪玩家，X轴来回移动
	* 在计时器控制下移动和绘图即可，也包含攻击判断和死亡判断
	* 怪物使用链表储存（删除方便）每个关卡设置不同因此8写了一个level文件
* 其他：菜单动画效果，画面切换效果，游戏结束效果


<br><br>编程乐趣
----------------------
* 让人物动起来最有意思了~虽然每次绘图都有点麻烦，而且还得把底色滤掉。但还是很开心
* 攻击和伤害的距离判断试了好久测算出来的，感觉挺精确的。（人物的攻击范围有限）
* 开始动画效果使用了一层黑色的图作遮罩，调节透明度来达到淡入淡出的效果，每个场景的切换也用到了这个技巧


<br><br>收获总结
----------------------
以后写这种代码多的程序一定会先考虑好用什么数据结构的…写这个游戏的时候花了一天的时间大改（哭泣）<br>
比起游戏编程感觉做效果的编程更有成就感呢XDDD
