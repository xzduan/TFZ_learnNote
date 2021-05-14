```
##
TFX
duanxz
20210508 10:04
```



```
### R version: 4.0.5
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
```

