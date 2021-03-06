
# 阴阳师自动御魂脚本

网易阴阳师电脑版，Autohotkey/Python 脚本，自动御魂, 已支持完全后台。

This is a script, written using Autohotkey and Python, for automated Yuhun farming in Netease game Onmyoji, PC emulator version.
Now the script supports fully background running. 

## 准备工作

玩家需自行下载网易阴阳师电脑版，并登录至游戏内，不要调整窗口大小。

该脚本为本人修仙时间使用 Autohotkey 1.1.28 版本编写，玩家可以自行下载 [Autohotkey](https://autohotkey.com/)，以及所有源文件，然后运行 onmyoji_yys-auto-yuhun.ahk。

__游戏窗口和AHK脚本都需要右键使用管理员权限运行！__

玩家也可以下载预先编译好的 AutoHotKey 可执行版本 [Releases](https://github.com/society765/yys-auto-yuhun/releases) 。

玩家还可以使用 Python 脚本 [py_onmyoji_yuhun.py](./py_onmyoji_yuhun.py)，Python 脚本需要以 __管理员__ 权限运行，脚本运行后自动开始，并需要在命令行用 Ctrl+C 中止。 
感谢 [#4](https://github.com/society765/yys-auto-yuhun/issues/4) 的反馈，Python 需要使用32位的版本，64位的可能会报错。

如果需要使用本地双开脚本，参考 [dual.py](./dual-SHUANG-KAI)。

## 使用方法及功能简介

玩家需要先进入探索灯笼-御魂-八歧大蛇-十层界面（或你想要挂机的层数），然后可以使用键盘快捷键(F10)开始运行脚本，鼠标不需要提前放在游戏窗口内。
但是如果有超过一个阴阳师游戏窗口，该程序可能无法找到正确的游戏窗口。

使用了后台插件，窗口现在可以完全后台，可以被遮挡，但是不能最小化。

该脚本为单人探索，每次消耗6体力。在脚本开始时会弹出对话框，输入对应的数字以选择自动点击中间或右边怪物。

玩家需要开启自动战斗模式，并提前准备好战斗阵容。御魂十层界面中的阵容 __需要__ 锁定。 
(2019.4.4更新后，该脚本不会再自动点击战斗中的“准备”)

在御魂战斗过程中，该脚本会自动拒绝所有悬赏封印的邀请。

该脚本仅使用了画面找色，鼠标后台点击的函数，完全模拟人类玩家行为，没有使用任何内存读写函数。在敏感位置添加了均匀分布的随机时间漂移，和随机坐标漂移。
作者使用过该脚本上万体力仍没有收到鬼使黑来信，而且作者不对您的可能存在的任何被封禁结果负责。  

不建议在御魂战斗中移动窗口位置，可能会导致战斗镜头漂移。

该脚本也适用于觉醒材料，和御灵。

玩家可以在任何时刻使用键盘快捷键结束脚本(F12)。

感谢您使用该脚本，并欢迎各种反馈和改进意见。 

## 已知存在的问题

* __2019/05/07, [#8](https://github.com/society765/yys-auto-yuhun/issues/8) 提出，如果使用点怪功能，系统会弹出一个对话框检测是否脚本。错误回答会导致鬼使黑来信。请玩家慎重使用！如果有对应的截图，欢迎打码后发Issue，这样方便作者修改脚本来添加对应的绕过机制。__

* 当玩家使用 Windows 7 系统时，需要以管理员身份运行阴阳师游戏窗口和脚本。而且，需要调整系统的画面设置： 右键我的电脑 -> 高级系统设置 -> 高级 -> 设置 -> 取消勾选以下3项： "启用 Aero peek"，"启用透明玻璃"，和"启用桌面组合"。

* 在 Windows 10 系统中，不需要调整系统画面设置。

* 玩家也可以使用旧版的按键精灵脚本，该按键精灵脚本不会再继续更新。按键精灵使用了后台点击，和前台找色函数，窗口不能被遮挡，不能被移动，但是不需要调整系统的画面设置。

* 作者把 AutoHotKey 代码用 Python 重写了一遍，目前 Python 代码可以正常运行，但是
  * 需要提前手动注册插件： `regsvr32.exe TSPlug.dll` 
  * 需要用管理员权限运行 Python 脚本 (以及游戏窗口) 
  * Python 脚本目前还不支持键盘快捷键 capture，只能手动运行脚本，
  以及通过任务管理器或 Ctrl + C 来终止 Python 进程。
  欢迎 PR 来添加键盘快捷键支持。

* Run `pip install pywin32` to install `win32com.client ` module for Python. 

## 更新记录

2018年1月13日，上传了初始版本。

2018年2月11日，强化了拒绝悬赏的函数。

2018年3月31日，完全使用 Autohotkey 重写了脚本，现在支持完全后台。

2019年4月4日，由于 Issue [#3](https://github.com/society765/yys-auto-yuhun/issues/3) 提及了 2019/3/28 更新后，战斗界面中的“准备”鼓面位置上移，导致脚本不能正确点击“准备”。为了避免以后类似情况的发生，作者注释掉了手动点击“准备”的函数，现在需要在御魂层数选择界面中，提前勾选“阵容锁定”。 

## 免责声明

网易，阴阳师，是网易公司的商标。 http://yys.163.com

按键精灵，是按键精灵公司的商标。 http://www.anjian.com

Autohotkey，为 GPL 开源程序。 https://autohotkey.com/

该脚本为了实现后台点击及找色功能，使用了开源的 [天使插件](http://bbs.tyuyan.net/thread-45659-1-1.html)，
该插件由 C++ 编写，用户可以前往他们的站点下载源代码，作者只是调用了预编译好的 dll 库。
并请参考天使插件的 License.

(如果上面`天使插件`地址不能访问，请尝试 [天使插件](http://52tc.info/thread-45659-1-1.html)，
好像他们论坛换地址了。)

<!-- 根据 [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) 开源协议，本人不对该脚本负任何责任。-->

## 协议 (License)

该源代码使用了 [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) 开源协议。

This project is licensed under the [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) license.

