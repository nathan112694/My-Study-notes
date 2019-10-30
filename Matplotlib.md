# matplotlib
## <font color = gray>matplotlib.pyplot</font>
plt.plot()原型
`plt.plot(x,y,format_string,**kwargs)`
`x,y` : x,y轴数据，列表或数组(可选）
`format_string`：控制曲线的格式字符串（可选）
`**kwargs`：第二组或更多，(x,y,format_string)
***
例：

```
import matplotlib.pyplot as plt
plt.plot([1, 2, 3, 4])
plt.ylabel(‘some numbers’)
plt.show()
```
运行结果如下：
![Alt text](https://i.loli.net/2019/10/29/adTK3o6qkUyjVZ5.jpg)


如果提供的是一个列表或者数组作为plot()的参数，<font color = red>Matplotlib就会默认把这个序列当作是Y轴上的值</font>，并且自动生成X轴的值，<font color = blue>默认情况下 ，X轴和Y轴向量长度相等，但是X轴会从0开始取值</font>。所以Y轴是[1，2，3，4]，而X轴是[0，1，2，3]。
***

plot() 还为每一对参数X和Y提供了一个可选的<font color = red>第三个格式化字符串参数</font>用来指定图形的颜色和线型。该格式化字符串的字母和符号均来自于MATLAB，由一个代表颜色的字符串和一个代表线型的字符串组合而成。默认使用的格式化字符串是’b-‘（表示蓝色实线）,红色圆点则是‘co’。
例 ：

```
plt.plot([1, 2, 3, 4],[1, 4, 9, 16],’ro’)
plt.axis([0, 6, 0, 20])
plt.show()
```

`plt.axis([xmin, xmax, ymin, ymax])`axis()命令列表作为参数来指定各个轴的视口大小(取值范围)。
***

```
import matplotlib.pyplot as plt
import numpy as np

a = np.arange(10)# arange()用于生成等差数列
# np.arange(10)表示生成从0到9的10个数
# np.arange(1,10)第一个参数是起始点，第二个参数是终止点，生成1到9的9个数
# np.arange(1，10，4)，第三个参数是代表公差，生成[1，5，9]

# 如果要生成多条曲线那么就必须给出X的参数了
plt.plot(a, a*1.5, a, a*2.5, a, a*3.5, a, a*4.5)#相邻的数据两两一组，分别表示X，Y的值
plot.show()
```
运行结果：
![Alt text](https://i.loli.net/2019/10/29/dEC1nfFbwAWBaez.jpg)


***
其他常用函数

### plt.xlabel():
对x轴增加文本标签

### plt.ylabel():
同理

### plt.title(): 
对图形整体增加文本标签

### plt.bar(): 
主要参数:(left, height, width)
<font color = green>(1)left:x坐标
(2)height:是柱的高度，一般height等于y的值
(3)width:柱的宽度（0～1，默认0.8）
还可以使用color设置颜色
(4)label：设置标签，并使用面向对象的命令，(5)plt.legend()显示标签</font>

### plt.xticks():
tick 刻度
tick label刻度注释
参数:(ticks，[labels])<font color = gray>（参数个数不确定）</font>

```
plt.xticks(np.arange(5),(‘A’,’B’,’C’,’D’,’E’))
```

### plt.yticks():
同上

###plt.subplot():
本函数可以在同一个图中绘制出多个子图
例子：

```
#参数间可以加逗号隔开也可以不加
plt.subplot(2,2, 1) #代表图像是2X2的第一行左边的图
plt.subplot(222) #代表图像是2X2的第一行右边的图
##也就是说前两个参数代表生成几乘几的图第三个参数代表是第几个图
plt.subplot(3,4,12) #3X4图像的第十二个图

```
***



