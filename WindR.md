```
##
TFX
duanxz
20210508 10:04
```

## Wind跨语言通用函数简介

| 函数     | 功能                                                         | 说明                                                         | 限制             |
| -------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---------------- |
| **WSD**  | 日期序列：获取选定证券品种一段时间内的历史序列数据,支持终端所有拥有万得代码（股票、债券、商品、外汇、基金和指数）的证券的日收盘行情 | 技术指标、技术形态、部分融资融券指标单次限取2000个单元格，大于2000个单元格，可分多次获取 | 每次限8000单元格 |
| **WSS**  | 多维数据：获取选定证券品种的历史截面数据,支持终端中股票、债券、商品、基金的基本资料、市场行情、证券分析、预测评级、财务数据、权益事件和投资组合数据 | 技术指标、技术形态、部分融资融券指标单次限取2000个单元格，大于2000个单元格，可分多次获取 | 每次限8000单元格 |
| **WST**  | 日内跳价：获取日内买卖十档盘口快照、成交数据,目前只支持上交、深交、中金、上期、大商、郑商的行情 | 可取最近7个交易日的数据；一次只能取1个Windcode               | --               |
| **WSI**  | 分钟序列：获取分钟行情数据、支持技术指标变参,目前只支持上交、深交、中金、上期、大商、郑商的行情 | 每次取一个code的时候，可以取最近3年数据(推荐使用此方法)；每次取多个code的时候，有如下限制：code数*天数<=100 | --               |
| **WSQ**  | 实时行情：获取订阅实时行情数据,支持终端支持的所有市场        | --                                                           | --               |
| **WSEE** | 板块多维：获取选定股票板块的历史界面数据                     | 支持多板块、多指标且板块数*指标数≤1000                       | --               |
| **WSES** | 板块序列：获取选定股票板块一段时间内的历史序列数据           | 支持多板块、但仅支持单指标提取多板块、单指标时，时间跨度＜250个交易日、板块数＜20提取单板块、单指标时, 时间跨度约800个周期 | --               |
| **WSET** | 数据集：获取板块成分、指数成分以及各证券品种的专题统计报表数据 | 停牌、复牌股票:一次最长获取一个月时间段内的数据;分红送转:一次最长获取10年时间段内的数据;期货合约持仓排名:一次最长获取一个月时间段内的数据 | --               |
| **EDB**  | 经济数据：获取宏观经济数据                                   | --                                                           | 每次限8000单元格 |

## 常见乱码问题

* Excel中，在to_csv（）中pd.read_csv(--------, encoding='utf-8')，如果乱码，可以换**utf_8_sig**，或者**gb18030**；
* 需要注意获取wind数据时的编码格式和数据库存储标准内的代码格式；



## 报错代码code对应解释

| ErrCode   | ErrMsg                        |
| --------- | ----------------------------- |
| -40520001 | 未知错误                      |
| -40520002 | 内部错误                      |
| -40520003 | 系统错误                      |
| -40520004 | 登录失败                      |
| -40520005 | 无权限                        |
| -40520006 | 用户取消                      |
| -40520007 | 无数据                        |
| -40520008 | 超时错误                      |
| -40520009 | 本地WBOX错误                  |
| -40520010 | 需要内容不存在                |
| -40520011 | 需要服务器不存在              |
| -40520012 | 引用不存在                    |
| -40520013 | 其他地方登录错误              |
| -40520014 | 未登录使用WIM工具，故无法登录 |
| -40520015 | 连续登录失败次数过多 |
| -40521001 | IO操作错误           |
| -40521002 | 后台服务器不可用     |
| -40521003 | 网络连接失败         |
| -40521004 | 请求发送失败         |
| -40521005 | 数据接收失败         |
| -40521006 | 网络错误             |
| -40521007 | 服务器拒绝请求       |
| -40521008 | 错误的应答           |
| -40521009 | 数据解码失败         |
| -40521010 | 网络超时             |
| -40521011 | 频繁访问             |
| -40522001 | 无合法会话           |
| -40522002 | 非法数据服务         |
| -40522003 | 非法请求             |
| -40522004 | 万得代码语法错误     |
| -40522005 | 不支持的万得代码     |
| -40522006 | 指标语法错误         |
| -40522007 | 不支持的指标         |
| -40522008 | 指标参数语法错误     |
| -40522009 | 不支持的指标参数     |
| -40522010 | 日期与时间语法错误   |
| -40522011 | 不支持的日期与时间   |
| -40522012 | 不支持的请求参数     |
| -40522013 | 数组下标越界         |
| -40522014 | 重复的WQID           |
| -40522015 | 请求无相应权限       |
| -40522016 | 不支持的数据类型     |
| -40522017 | 数据提取量超限       |
| -40530001 | 数据错误                |
| -40530002 | 未初始化                |
| -40530003 | 功能号错                |
| -40530004 | 用户已登出或无此LogonID |
| -40530005 | 回报队列已满            |
| -40530006 | 发送请求失败            |
| -40530101 | 未通过认证             |
| -40530201 | 获取配置错误           |
| -40530202 | 券商（期货商）代码错   |
| -40530203 | 登录代码错             |
| -40530204 | 账号密码错             |
| -40530205 | 账号类型错             |
| -40530206 | 登录失败次数过多       |
| -40530301 | 建立连接失败           |
| -40530302 | 处理超时               |
| -40530401 | 交易代码错             |
| -40530402 | 价格委托方式错         |
| -40530403 | 委托数量错             |
| -40530404 | 交易方向错             |
| -40530405 | 市场代码错             |
| -40530406 | 投机套保字段错         |
| -40530407 | 委托队列满             |
| -40530501 | 撤单委托序号错         |
| -40530502 | 委托状态不可撤单       |
| -40530601 | 查询过于频繁           |
| -40530602 | 回报数据已被新请求覆盖 |
| -40530603 | 获取回报数据超出记录数 |
| -40530604 | 多于一个的查询条件     |
| -40530605 | 无对应请求流水号记录   |
| -40530606 | 无对应委托回报         |
| -40530607 | 委托失败               |
| -40530608 | 委托已发送             |



## R

```
### R version: 4.0.5
```

```
### 如果wind的代码生成器（cg）无法打开，点开任务管理器关闭“WindNavigator”进程后，再重新打开
```

```
## 读数据
dataTest210524 <- read.table(file = "smpp210524.txt",header=FALSE,sep=' ',na.strings = c("NA"),fileEncoding = 'utf-8')
##
colnames(dataTest210524)<- c('name','total','recent_1Y','drawdown')

ggplot(data=dataTest210524,aes(x=drawdown,y=total))+geom_point(aes(col=factor(name),size=1.2))  +geom_smooth(method="lm",se=T)


```





```
require(WindR)

## 时间序列
## wdata<-w.wsd（codes, fields, beginTime, endTime, ..., options）

maotai_data_3Day <- w.wsd(codes='600519.SH',fields = 'CLOSE,HIGH,LOW,OPEN',beginTime = '-3D')


## 日截面
## wdata<-w.wss（codes, fields, ..., options）

wdata_test<-w.wss(c('600000.SH,000002.SZ,000009.SZ,000012.SZ,000021.SZ'),fields = c('comp_name,comp_name_eng,ipo_date,float_a_shares,mf_amt,mf_vol'),tradedate='20210507');


## 分钟数据(example: break = 3min)
## wdata<- w.wsi(codes, fields, beginTime, endTime, ..., options)

wdata_test2 = w.wsi(codes = 'IF00.CFE',fields = 'open,high,low,close',begintime = Sys.Date( )-1,endtime = Sys.time( ),BarSize=3);

## 获取全球宏观经济数据函数EDB
## wdata<-w.edb(codes, beginTime, endTime, options)

xx_test <- w.edb('M1002661','2021-01-01','') 
ggplot(data= NULL, aes(x = xx_test$Data$DATETIME, y = xx_test$Data$CLOSE)) + geom_point(color = "orange")+xlab('')+ylab('')+labs(title = "国债即期收益率：6个月")

```



```
ps:
##WindR返回的日期采用POSIXct格式。以浦发银行、平安银行和招商银行的IPO日期为例：

w.wss('600000.SH,000001.SZ,600036.SH','ipo_date')$Data$IPO_DATE
[1] 36474 33331 37355

## 如需转换成DateTime格式，可以使用WindR提供的asDateTime函数：

> w.asDateTime(c(36474, 33331, 37355))
[1] "1999-11-10 00:00:00 CST" "1991-04-03 00:00:00 CST" "2002-04-09 00:00:00 CST"


### data类型与时间戳数值格式的转换
require('dplyr')
Sys.time() %>% as.numeric()
Sys.time() %>% as.numeric() %>% .POSIXct()

### 时分秒数据离散记录，返回list
unclass(as.POSIXlt(now))
```





## python

```
### python
# jupyter中pip新的包时，前面加个感叹既可
! pip install schedule
```

### 数据格式的互相转换和读写

**pandas可以to_json()，也支持直接to_sql()进入数据库**

参考：[在pandas.DataFrame.to_sql时指定数据库表的列类型](https://www.jianshu.com/p/4c5e1ebe8470)

```
## 存储为json的方法：先构造df，然后利用panda库的to_json函数

[pandas 之 DataFrame 保存为文件df.to_csv、df.to_json、df.to_html、df.to_excel](https://blog.csdn.net/tz_zs/article/details/81137998)

[to_json的官方文档](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_json.html)

[中文乱码出现时](https://blog.csdn.net/FontThrone/article/details/75212825)
```

```
## json的读写
## JSON在python中分别由list和dict组成。

with open("../config/record.json","w") as dump_f:
    json.dump(load_dict, dump_f)
    
with open("../config/record.json",'r') as load_f:
    load_dict = json.load(load_f)

#print(load_dict)
```

| Python                                 | JSON   |
| -------------------------------------- | --------------- |
| dict                                   | object |
| list, tuple                            | array  |
| str                                    | string |
| int, float, int- & float-derived Enums | number |
| True                                   | true   |
| False                                  | false  |
| None                                   | null   |

```
## 读取txt和写csv
import pandas as pd
from WindPy import *
from datetime import *
import time
import numpy as np

data = pd.read_table('C:\\getpricelist.txt',header=None,encoding='gb2312',delim_whitespace=True)
data.columns=['stkcd','evendate']

df = pd.DataFrame(np.transpose(totalist), columns=['stkcd', '证券名称', '收盘价', '涨跌幅', '交易日期'])
print(df)
df.to_csv("Y:\\个股日交易数据.csv", sep=',', mode='a',encoding='gb18030')
```
### 纯文本文件的写入(txt)

```
# 此方法的缺点是：如果range()的大小十分恐怖，会因为大量的文件读取操作而特别慢
for tempIndex in range(100):
    with open('test.txt','a') as file0:
        print('|close|%s |自己|%s |他人|%s |差值| %s' %(tempIndex,tempIndex+1,tempIndex+2,1),file=file0)
```

### 文件处理和判断

```
# 判断文件 / 文件夹是否存在
os.path.exists() 
#方法用于检验文件 / 文件夹是否存在。

# 判断文件是否为空
os.path.getsize() 
#返回文件的字节数，如果为 0，则代表空。
```

```
# 注释
'''
 注释
'''

# 字符串操作——截取掉后3位
tempStr[:-3]
```

### 定时函数

[Python 定时任务的实现方式](https://blog.csdn.net/songlh1234/article/details/82352306?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522162158409216780357273095%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=162158409216780357273095&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-2-82352306.first_rank_v2_pc_rank_v29&utm_term=Python%E5%AE%9A%E6%97%B6&spm=1018.2226.3001.4187)



### 策略的实现和一些基本的Wind函数实操

```
### 策略实现案例（期货）
双均线策略（均线穿梭生成的买卖时机获取）
dual thrust（通道突破原则）
R-breaker（日内交易，主要策略为趋势跟随和趋势反转）
alpha对冲
网格交易
跨品种套利
跨期套利
做市商交易
海龟交易法

## 原始来源：
https://blog.csdn.net/u011078141/article/details/89453203
## 该博主的个人代码分享页面：
https://www.myquant.cn/docs/python_strategyies/153
```

[策略实现案例](https://www.myquant.cn/docs/python_strategyies/153)



```
from WindPy import *

import json

w.start();
```

```
## 获取A股代码
AllAStock =w.wet("SectorConstituent","date=20210517;sectorld=a001010100000000;field=wind_code");
## 结果保存至文件中
with open('AllAStock.json',mode='w') as f2:json.dump(AllAStock.Data[0],f2);
```



```
## 获取全体非停牌和st的a股代码
import pandasas pd
import numpyas np
import datetime
from WindPy import *

## 获取当天时间
date = datetime.today()

## 定义路径，判断不存在则新建
folder_target = "C:\\stocks\\"
if os.path.exists(folder_target) == False:
    os.mkdir(folder_target)
    
#1.获取全部a股数据
all_a = w.wset("SectorConstituent",date = date ,sector=u"全部A股")

#获取所有a股代码
all_Code = list(pd.Series(all_a.Data[1]))#获取的是列表数据

#2.获取当天所有停牌股票信息
all_tp = w.wset("TradeSuspend",startdate = date,enddate = date,field = "wind_code,sec_name,suspend_type,suspend_reason")
all_tp_code = list(pd.Series(all_tp.Data[0]))

#3.剔除ST
all_st = w.wset("SectorConstituent",date=date,sector=u"风险警示股票",field="wind_code,sec_name")
all_st_code = list(pd.Series(all_st.Data[0]))

#4.获取当天剔除ST和停牌的全部A股代码
all_Code = set(all_Code)
all_st_code =  set(all_st_code)
all_tp_code = set(all_tp_code)

code = all_Code - all_tp_code - all_st_code

#再将code转换为列表形式
code = list(code)
print(code)
```

```
## w.wsd()数据并转化成dataframe格式
wsd_data=w.wsd("510050.SH", "close,NAV_acc", "2005-02-23", "2017-07-11", "")
 
fm=pd.DataFrame(wsd_data.Data,index=wsd_data.Fields,columns=wsd_data.Times)

#转置
fm=fm.T 
```

### Wind的实时行情API的使用WSQ

参考: [Wind的实时行情API的使用](https://blog.csdn.net/qtlyx/article/details/107291342?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522162130303416780366595177%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=162130303416780366595177&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_v2~rank_v29-17-107291342.first_rank_v2_pc_rank_v29&utm_term=Wind%E9%87%8F%E5%8C%96&spm=1018.2226.3001.4187)

Wind的实时行情是通过**回调函数**来实现的。也就是大框架下，我们是让主程序一直while循环，然后有新的行情到来的时候，wind的API会自动调用我们写好的回调函数。

    if __name__ == '__main__':
     
        w.wsq("000002.SZ,2202.HK",
                  "rt_date,rt_time,rt_last,rt_ask1,rt_bid1,rt_asize1,rt_bsize1", func=AH_raio_calculatte)
        while True:
            pass
首先，在主程序里面，很明显，就是设置好我们需要的行情内容。

设置完需要的数据和回调函数的名称之后，就把主线程打入死循环即可。例子中func_name：AH_raio_calculatte；

在新的行情到来的时候，wind会自动把新的行情数据传递给我们的回调函数，我们的函数要做的事情就是解析一下回调函数中的数据，并实现自己想要的功能。

