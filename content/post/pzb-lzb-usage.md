+++
date = '2025-01-08T17:24:21+08:00'
draft = false
title = 'PZB/LZB的那些故事'
+++

*注：部分由AI生成*


在模拟火车游戏中，尤其是涉及德国铁路（DB）的列车驾驶时，一些新手可能好奇那个叫做PZB的开关是啥。打开后，油门杆一到底，马上就被Zwangsbremsung了。因此掌握PZB（磁感式列车安保系统）和LZB（线性列车控制系统）的使用方法是至关重要的。本文将详细介绍这两个系统的操作，包括确认、缓解、越过红灯的操作步骤，以及限速处理策略。

#### 一、PZB系统使用方法

PZB系统主要用于确保列车在行驶过程中的安全，特别是在遇到不同信号时采取相应的操作。

**1. 确认操作**

当列车接近预告信号（非绿灯）或预告限速牌时，需要进行确认操作。如果预告信号旁边带有PZB磁铁，列车通过前，司机需在4秒内按下应答键。此时，1000Hz灯号会亮起，提示司机在29秒内将列车速度降至指定速度以下（客车85km/h，轻货车70km/h，重货车55km/h）。

**2. 缓解操作**

当列车安全通过主信号机且信号为绿灯或绿黄灯时，可以按下释放键（通常为键盘上的End键）进行缓解操作。此时，蓝色数字灯会停止闪烁，列车可以恢复到指定速度。


**3. 越过红灯操作**

在特殊情况下，如遇到紧急情况必须越过红灯时，应按住命令Befehl键（通常为键盘上的Delete键），以不超过40km/h的速度通过红灯。当白色灯号“Befehl40”亮起时，可以放开命令键，并继续小心驾驶。

**4. 限速处理**

在行驶过程中，列车必须严格遵守预告限速和主信号机的限速要求。如果预告限速低于指定速度，则以预告限速为准。在接近主信号机时，如果信号为红灯，列车需在150米内降至500Hz速限（客车65km/h，轻货车45km/h，重货车35km/h），并在红灯前完全停止。

**5. 紧急制动**

在以下情况下，会导致一个PZB紧急制动被触发：

- 未及时按动确认按钮确认1000hz磁铁
- 响应信号后，未及时减速到对应车速
- 通过一个h/v信号（一般以连续3个磁铁的形式出现）时远超路段限速（2000hz触发）
- 通过红灯/调车信号（一红+几个小白灯）未**按住**Befehl按钮
- 其他可能的情况……

触发时，1000hz指示灯会闪烁，部分列车上会亮起一个红色的“S”灯号。

![pzb紧急制动](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20241221191952_1.jpg)

*图：pzb紧急制动*

待列车完全静止后，按动缓解按钮即可缓解制动。

#### 二、LZB系统使用方法

LZB系统提供了更为灵活的限速控制，通常用于高速线路或新线路。

**1. 自动驾驶**

LZB系统启用时，列车会自动根据预设的浮动速限进行驾驶。此时，PZB系统处于bypass状态，不需要进行应答操作。浮动速限会显示在时速表上，司机只需确保列车速度不超过浮标速限即可。

**2. 区间结束处理**

在LZB区间结束前，ende指示灯会闪烁（如下方图片），提示司机按下PZB释放键。按键后，ende指示灯保持常亮并持续至LZB区间结束。区间结束后，列车会自动回到PZB模式，此时需按照PZB系统的要求进行确认和缓解操作。

**3. 限速处理**

在LZB模式下，如果AFB（定速巡航系统）速限杆推至某个位置，列车会自动加速至该速限，但不会超过LZB的浮动速限。因此，司机可以通过调整AFB速限杆来控制列车的加速力道，同时确保不超过LZB的限速要求。

# 图片

![3个pzb/lzb按钮](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180121_1.jpg)

*图：3个pzb/lzb按钮，从左到右：befehl、缓解、确认*

![处在lzb区间的列车，限速100](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180252_1.jpg)

*图：处在lzb区间的列车，限速100*

![预告信号](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180344_1.jpg)

*图：预告信号，左侧下一个为绿灯，右侧下一个为红灯，按pzb确认按钮*

![预告限速，13x10=130](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180438_1.jpg)

*图：预告限速，13x10=130*

![lzb ende指示/即将退出lzb](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180527_1.jpg)

*图：LZB ende指示/即将退出LZB*

![处于pzb O模式下的列车](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180628_1.jpg)

*图：处于pzb O模式下的列车*

![信号示例](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180819_1.jpg)

*图：信号示例，此处本机与下个信号均为绿灯，下个预告限速80*

![确认的1000hz磁铁](https://raw.githubusercontent.com/sysdl132/lfs/refs/heads/img/website-static/20250108180928_1.jpg)

*图：按动确认按钮后，1000hz指示灯常亮*