# SunAnimation
仿华为天气应用的日落日出动画效果，通过动画，动态的显示当前太阳轨迹并停在当前所处的位置。

#### 效果图

![avatar](/ScreenShort/short.png)

#### 主要思路

1. 自定义view，通过attrs.xml文件配置需要的属性，包括圆弧的颜色、字体颜色等；
2. 绘制日落时间到日出时间的圆弧；
3. 通过当前时间与总时间的比，计算出需要动态画弧的角度；
4. 通过属性动画获取当前角度，并通过角度计算出当前点的坐标(这一步比较关键，比如现在是中午12点，那么通过point(x,y)来记录在圆弧上的位置)；
5. 实时绘制(通过属性动画，传入角度以及动画时间，监听实时的进度，计算出point(x,y)，在调用invalidate()刷新view)；

整体来说，实现这个效果比较简单，如果在项目中遇到类似的需求，可以参考该实现思路。
