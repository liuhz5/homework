# Construct2 制作枪战小游戏
## 一、安装Construct 2
如果你还没有construct 2,请前往官网获取最新版本的Construct 2，选择free版本就可以满足我们制作枪战小游戏的需要。Construct 2编辑器仅适用于Windows，但是您制作的游戏可以在任何地方运行，这使得游戏的便携性、传播性大大提高。
## 二、开始制作游戏
### 新建游戏
&ensp;&ensp;&ensp;现在你便拥有Construct 2，打开它并点击文件按钮，然后选择“新建”。  
![](http://gamerboom.com/wp-content/uploads/2012/05/file-newfrom-scirra.com_.png)

&ensp;&ensp;&ensp;新项目对话框中你不需要改变任何选项，只需要点击“创造”项目便可。Construct 2将始终保持项目作为一个单一的.capx文件。而现在我们需要着眼于空白的布局——这是你所创造的设计视图以及目标位置。布局就像是一个游戏关卡或屏幕上的菜单。而如果你使用的是其它工具，这一布局就是空间，场景或框架一样的存在。
### 插入对象
&ensp;&ensp;&ensp;我们想要的第一件事是重复的背景。该平铺背景对象可以为我们做到这一点。首先，这是您的背景纹理 - 右键单击​​它并将其保存到你的计算机的某个地方：

![](https://www.scirra.com/images/articles/bg.png)

&ensp;&ensp;&ensp;现在，双击布局中的一个空格来插入一个新的对象,一旦出现“ 插入新对象”对话框，双击“平铺的背景”对象以插入它。

![](https://www.scirra.com/images/articles/insertobject.png)

&ensp;&ensp;&ensp;现在，你应该在布局中看到平铺的背景对象。让我们调整它以覆盖整个布局。确保选中它，然后左侧的属性栏应显示对象的所有设置，包括其大小和位置。将其位置设置为0,0（布局的左上角），并将其大小设置为1280,1024（布局的大小）。

![](https://www.scirra.com/images/articles/tiledproperties.png)
### 添加层面
&ensp;&ensp;&ensp;布局总是包含多个层面，你可以在此为对象进行分组。图像层面就像是玻璃片一样堆积在每个列表上，并且其表面也附着了各种对象。如此你便能够更轻松地思考该将哪些对象置于上方，该隐藏或锁定哪些对象，并进一步明确视差效果等。举个例子来说吧，在一款游戏中我们希望将所有内容呈现在背景图层之上，所以我们便在其它对象之上创造了另外一个层面。
&ensp;&ensp;&ensp;为了管理层面，请点击“层面”标签,对层面进行命名（Construct 2的计数是从0开始，因为在编程中这样的设置更合适）。

![](http://gamerboom.com/wp-content/uploads/2012/05/layers-tabfrom-scirra.png)

&ensp;&ensp;&ensp;修改后的层面显示如下:

![](http://gamerboom.com/wp-content/uploads/2012/05/layers-barfrom-scirra.png)

### 添加输入对象
&ensp;&ensp;&ensp;首先，将注意力转回布局。双击以插入另一个新对象。这次，选择Mouse对象，因为我们需要鼠标输入。对Keyboard对象再次执行相同操作。（这些对象不需要放置在布局中。它们是隐藏的，并自动在项目范围内工作。现在我们项目中的所有布局都可以接受鼠标和键盘输入。）

&ensp;&ensp;&ensp;插入游戏对象：  
玩家：

![](https://www.scirra.com/images/articles/player.png)

怪物：

![](https://www.scirra.com/images/articles/monster.png)

子弹：

![](https://www.scirra.com/images/articles/Bullet.png)

爆炸：

![](https://www.scirra.com/images/articles/explode.png)

### 添加行为
&ensp;&ensp;&ensp;让我们为玩家添加8方向移动行为。单击播放器以选择它。在属性栏中，请注意“ 行为”类别。单击“ 添加/编辑”。播放器的“行为”对话框将打开。

![](https://www.scirra.com/images/articles/openbehaviors.png)

单击行为对话框中的绿色“添加行为”图标。双击8方向移动以添加它。


![](https://www.scirra.com/images/articles/add8dir.png)

&ensp;&ensp;&ensp;再次执行相同操作，这次添加Scroll To行为，使屏幕跟随播放器，以及绑定到布局行为，以使它们保持在布局中。行为对话框现在应如下所示：

![](https://www.scirra.com/images/articles/playerbehaviors_2.png)

将Bullet移动和Destroy外部布局添加到Bullet对象

将子弹移动添加到Monster对象

将Fade行为添加到Explosion对象

同时利用克隆功能创造更多的怪物！

### 添加活动
&ensp;&ensp;&ensp;首先，单击顶部的“ 事件表1”选项卡以切换到“ 事件”表编辑器，并对对象添加活动，添加活动后表格如图：

![](https://github.com/liuhz5/hz-homework/blob/gh-pages/20171007154452585.png)

至此，游戏制作就完成了！




## 成果展示：
![](https://github.com/liuhz5/hz-homework/blob/master/QQ%E5%9B%BE%E7%89%8720181011133626.gif)

![](https://github.com/liuhz5/hz-homework/blob/master/QQ%E5%9B%BE%E7%89%8720181011133626.gif)