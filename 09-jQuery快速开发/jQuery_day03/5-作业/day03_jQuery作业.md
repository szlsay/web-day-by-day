## 本资源由 itjc8.com 收集
# 每日作业-jQuery第03天

### 1 - 按键变色（加强训练）

- 题目描述

   按键变色主要考察时间对象event的属性的使用，可以类比DOM中的event获取按键值：

   1）按下键盘键触发事件

   2）根据所按键盘的字母给盒子上自定义背景色

![001](images/001.png)

- 训练目标

  学会使用 jQuery 的event。

- 训练提示

  1.绑定事件，获取按键值

  2.条件判断，给盒子上色



###    2 - 背景色插件（加强训练）

- 题目描述

  点击按钮，改变div的背景色，jQuery中的animate()不能实现背景色渐变，需要引入插件。

  ![002](images/002.png)



- 训练目标

  学会使用插件

- 训练提示

  1.先引入jQuery，然后在引入jQuery插件：jquery.color.js

  2.常规调用animate() 该方法得到增强。


###    3 - 五星好评（综合练习）

- 题目描述

  鼠标进入五角星，当前和之前的所有五角星变为实心，后面的是空心。点击记录该五角星，鼠标移开后该记录点之前所有变为实心，之后的所有变为空心。

  ![003](images/003.png)



- 训练目标

  培养使用jQuery综合处理需求能力。

- 训练提示

  1.鼠标进入某个五角星，当前和之前的所有五角星变为实心，后面的是空心。

  2.鼠标点击某个五角星，记录该五角星

  3.鼠标移开后该记录点之前所有变为实心，之后的所有变为空心。

### 4 - 旋转木马（综合练习）

- 题目描述

  点击右侧箭头显示下一张，点击左侧箭头显示前一张。

  ![004](images/004.png)

  ​

- 训练目标

  综合练习，使用jQuery解决复杂需求逻辑。

- 训练提示

  1.5张图片位置信息设置为一个数组，数组中有五组数据。

  2.页面加载的时候，五张照片分别设置为数组中的样式。

  3.点击左右两侧按钮，改变数组中样式的位置，重新加载。
