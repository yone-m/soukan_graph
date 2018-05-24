# soukan_graph
for making a graph of soukan-function


<img src="https://github.com/shutokawabata0723/soukan_graph/blob/master/graph_soukan.png" width="500px">

## IN
test.csv

# Code
```python
import seaborn as sns
import pandas as pd
import csv


pal = []
a = open('test.csv','r')
for i in a:
    i = i.rstrip().split(',')
    ID = int(i[0])
    kakaku = int(i[1])
    kyori = float(str(i[2]))
    LINE = [ID,kakaku,kyori]
    pal.append(LINE)

# 背景の設定
sns.set_style("whitegrid")

# データセットの作成(palは二次元配列）
tips = pd.DataFrame(pal,columns=('ID','kakaku','kyori'))

# データセットのコラムを指定してグラフ描写
sns.regplot(x="kyori",y="kakaku",data=tips)
```



# Author
ShutoKawabata
