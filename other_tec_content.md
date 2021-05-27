```
##
TFX
duanxz
20210507 16:24
```



### markdown

[Markdown公式、符号](https://blog.csdn.net/weixin_42782150/article/details/104878759)



[markdown语法教程](https://markdown.com.cn/basic-syntax/links.html)



### R

[R语言的常用的包](https://blog.csdn.net/ToyPython/article/details/92800013)



### 本地的回测工程

[本地量化工具集成开源量化框架backtrader操作指南](https://blog.csdn.net/hangzhouyx/article/details/108178289?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522162130303416780366595177%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=162130303416780366595177&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_v2~rank_v29-22-108178289.first_rank_v2_pc_rank_v29&utm_term=Wind%E9%87%8F%E5%8C%96&spm=1018.2226.3001.4187)

[量化交易平台搭建-盈宽量化-实操指导](https://blog.csdn.net/ufobizsoft/article/details/85274663?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522162130303416780366595177%2522%252C%2522scm%2522%253A%252220140713.130102334.pc%255Fall.%2522%257D&request_id=162130303416780366595177&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_v2~rank_v29-27-85274663.first_rank_v2_pc_rank_v29&utm_term=Wind%E9%87%8F%E5%8C%96&spm=1018.2226.3001.4187)



### python

### 取模

$$
a\%b
$$

取模结果其实为余数。额外需要注意的是，

* python中取模的余数符号与b的符号需要一致，例子如下：

```
print(7%4)
print(17 % -4)
print(-7%4)
print(-17 % -4)

结果：
3
-3
1
-1
```

* 取模运算的两个操作数a和b可以是整数，也可以是浮点数

#### 爬虫

```
核心注意：
1. 界面是否存在反扒处理。频繁访问受限的话，考虑将<body> </body>存在本地；
2. 不一定从查看器里获取数据。如果network中有后台请求和对应访问返回的明细，这个可能更简单直接一点；
```



[selenium webdriver 启动三大浏览器Firefox,Chrome,IE](https://blog.csdn.net/azsx02/article/details/68947429/?utm_medium=distribute.pc_relevant.none-task-blog-baidujs_title-1&spm=1001.2101.3001.4242)

```
pip install selenium
selenium模块是python爬虫中一个解决一些网页反爬虫的一个有效手段，可以使用它来模拟人操作浏览器的行为

# ps：如果版本一致检查python安装路径有没有添加到环境变量里面，***driver.exe文件需要放在python.exe所在文件夹下

#以火狐为例进行测试
from selenium import webdriver

browser = webdriver.Firefox()
login_url = 'https://www.baidu.com';
browser.get(login_url)
#此处会直接打开一个测试工具窗口在可视化界面中，访问对应url
```

```
from selenium import webdriver
from selenium.webdriver.common.action_chains import ActionChains
from time import sleep

# 打开火狐浏览器
browser=webdriver.Firefox()

# 打开百度首页
browser.get("https://www.baidu.com/")

# 在输入框输入'hello world'
browser.find_element_by_id("kw").send_keys("hello world")

# 点击'百度一下'按钮
browser.find_element_by_id("su").click()

# 清除搜索框内容
browser.find_element_by_id("kw").clear()

# 调用js代码
js="alert('hello world');"
browser.execute_script(js)

# 关闭浏览器
sleep(1)
browser.quit()
```



```
# 本地文件
path = 'd:/Download/mydoc.html'
htmlfile = open(path, 'r', encoding='utf-8')
htmlhandle = htmlfile.read()
from bs4 import Beautifulsoup
soup = Beautifulsoup(htmlhandle, 'lxml')

# 此处可以根据html的布局，选择获取所有div，span，a等各种标签。
# 标签内的文本直接用.get_text()，获取，如果是标签内的class或者tittle或者href等属性，直接用***[‘href’]进行获取既可

for item in test_html.find_all('div'):
    if '管理期货' in item.get_text():
        # print(item.get_text() + '5555555555555555555')
        new['res'] = item.get_text();
        result01 = result01.append(new, ignore_index=True)
```



[python解析本地HTML文件](https://blog.csdn.net/sinat_38682860/article/details/108752360)

[使用Beautifulsoup解析本地html文件](https://blog.csdn.net/fwj_ntu/article/details/78843872)

> ```python
>  BeautifulSoup方法打开
>  核心方式为：
>  x.find('div',{'class','related'}).findAll('a')
> ```



[Python爬虫如何爬取内容（html）和解析内容](https://blog.csdn.net/Strive_0902/article/details/84201690)

> [XPath 语法_W3school](https://www.w3school.com.cn/xpath/xpath_syntax.asp)
>
> \# 如果搜索部分在etree中存在固定结构，利用类似正则表达的方式获取
>
> \# F12界面中，查看器对应部分直接右键-copy-xpath，竟然可以直接获得准确的表达方式，真的离谱
>
> import lxml
>
> \# 获取到响应的内容后，采用etree的HTML方法，返回DOM树型结构的根节点
> html = etree.HTML(response.text)     
>
> \# 采用etree的xpath方法，定位到我们需要的东西
>
> ans = html.xpath('//div[@class = "billboard-bd"]//tr/td/a/text()')  



[python爬取私募排排网基金产品心得](https://blog.csdn.net/yukou123/article/details/100980348)

[运用 Python 爬取私募基金信息_request](https://blog.csdn.net/luckycdy/article/details/84342640)

> 私募排排网的各产品/公司的单页面爬取
>
> 设计cookie问题，验证问题
>
> 连接mysql和访问直连存储

