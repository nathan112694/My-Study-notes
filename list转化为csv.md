#将list转存为csv文件
```
#错误代码
list = [[1, 2, 3],[4,5,6],[7,8,9,]]
list.to_csv(‘e:/testcsv.csv’,encoding = ‘utf-8’)
```
运行后出现：
![Alt](https://i.loli.net/2019/10/27/Rhv4yOVMFZTCsem.jpg)
list没有to_csv属性，也就是说<font color = red>list无法直接转存为csv</font>
为了解决这个问题，我们可以引入<font color = green>pandas </font>模块，使用其<font color = green>DataFrame</font>属性

```
import pandas as pd

list = [[1, 2, 3],[4,5,6],[7,8,9,]]
#下面这行代码为错误代码
#list.to_csv(‘e:/testcsv.csv’,encoding = ‘utf-8’)# 变长字节的编码方式，如果没有设置则是默认ASCII编码
name = [‘one’,’two’,’three’]
test=pd.DataFrame(columns = name, data = list)#数据有三列，列名分别为one，two，three
print(test)
test.to_csv(‘e:/testcsv.csv’,encoding = ‘gbk’)	#gbk即‘’国标‘’，‘’扩展‘‘的缩写，国际标准扩展集
```
运行结果如下：
 

| |one|two|three|
|----|:----:|:----:|:----:|
| 0|1|2|3|
|1|4|5|6|
|2|7|8|9|

![Alt](https://i.loli.net/2019/10/28/29S8kH6RcXzmJiF.jpg)

默认的行名是从0开始递增的数字，要是不喜欢这个表示，也可以自己修改，只要在pd.Data.Frame()中定义一个index参数，具体如下：

```
import pandas as pd

list = [[1, 2, 3],[4,5,6],[7,8,9,]]
name = [‘one’,’two’,’three’]
name2 = [‘a’,’b’,’c’]
test = pd.DataFrame(columns = name, index = name2, data = list)
print(test)
test.to_csv(‘e:/testcsv.csv’,encoding = ‘gbk’)
```
结果如下：![Alt text](https://i.loli.net/2019/10/28/YOivd7a2MckAZWn.jpg)
