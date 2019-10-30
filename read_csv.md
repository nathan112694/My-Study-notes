# pd.read_csv()
## 格式 
![Alt](https://i.loli.net/2019/10/27/waj3V6fDHYckLMy.jpg)

## 常用参数
`filepath_or_buffer` 
（这是<font color = red> **唯一一个必须要有** </font>的参数）文件所处的路径
***
`sep`
指定分隔符，默认为逗号
***
`delimiter` 
定界符，备选分隔符（如果指定该参数，则sep失效）
***
`header`
指定哪一行作为表头。默认设置为0（即第一行作为表头），如果没有表头的话，要修改参数，设置header = None

```

import pandas as pd
data = pd.read_csv(r”D:\\testData.csv”)
data.head()

# 因为这里没有设置header参数
# 所以默认header = 0
# 要是设置header = 1 则把第二行当作表头
# 第一行的passenger和class就显示不出了

```


| |panssenger <font color = red>（表头）</font> |class <font color = red>（表头）</font>|
|----|:----:|:----:|
|0|Sam|A|
| 1|Lily|B|


```
data1 = pd.read_csv(r”D:\\testData.csv”,header = None)
data1.head()
#可以看到原本的表头都被当成数据使用了
```


| |0 <font color = red>（表头）</font> |1 <font color = red>（表头）</font>|
|----|:----:|:----:|
|0|passenger|class|
|1|Sam|A|
|2|Lily|B|

***
`names`
指定<font color = red>列的名称</font>,用列表表示。一般没有表头，即header = None时，这个用来添加列名就很有用。<font color = green>如果文件中不包含header的行，应该显性设置header = None</font>

```
data2 =  pd.read_csv(r”D:\\testData.csv”,header = None,name = [‘a’,’b’])
data2.head()
```


|       |a        |       b|
|-------|:-------:|-------:|
|0      |passenger|class   |
|1      |Sam      |A       |
|2      |Lily     |B       |

***
`skiprows`
需要跳过的行号列表（从0开始，或者说从csv的第一行开始）

```
data3 = pd.read_csv(r”D:\\testData.csv”,skiprows = 1,header = None)
data3.head()
```


||0|1|
|----|:----:|:----:|
|0|Sam|A|
|1|Lily|B|

***
`usecols`
返回一个数据子集，该列表的值必须可以对应到文件中的位置（数字可以对应到指定的列）。例如：usecols有效参数可能是[0,1],也可以是[‘passenger’,’class’]
***
`nrows`
需要读取的行数（从0开始或者说从Excel的第一行）
***
不管进行了什么操作，最后都是从csv第一行开始显示
