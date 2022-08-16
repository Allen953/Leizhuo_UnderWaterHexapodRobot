# Leizhuo_UnderWaterHexapodRobot

如果无从下手，不知道怎么用。

可以先看一下文件夹7.Photos & Videos里面的视频。

里面的视频是教学视频。可以帮你快速把功能包在自己的ubuntu电脑上跑起来。

实物照片：

![实物照片1](https://github.com/Allen953/Leizhuo_UnderWaterHexapodRobot/blob/main/7.Photos%20%26%20Videos/QQ%E5%9B%BE%E7%89%8720220815123440.jpg)

关节标定：

首先，用程序驱动18个舵机，让18个舵机都转到中位，即90度的位置（180度舵机旋转范围为0~180度，所以90度时是舵机中位）。

然后按照下图的方式，将18个机械关节垂直安装好，这样关节就标定好了。但是由于实际情况下，无法使得关节扣上去的时候刚好垂直，因此我们我们实际需要加入补偿量进行修正。

![关节标定](https://github.com/Allen953/Leizhuo_UnderWaterHexapodRobot/blob/main/7.Photos%20%26%20Videos/%E6%A0%87%E5%AE%9A%E5%9B%BE%E4%BE%8B2.png)


步态规划：

![步态规划](https://github.com/Allen953/Leizhuo_UnderWaterHexapodRobot/blob/main/7.Photos%20%26%20Videos/QQ%E5%9B%BE%E7%89%8720220815125429.png)

