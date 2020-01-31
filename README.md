# 2019-nCoV

## 说明

使用d3js复刻网易新闻的[新型肺炎疫情地图](https://news.163.com/special/epidemic/)。

大步骤：

1. 从原始实现（echarts）摘出最小代码，调整到可运行状态。
2. 使用d3js实现。

## 步骤

### 地图数据

https://github.com/d3cn/data/blob/master/json/geo/china/china-province.geojson

* 注意：没有南海诸岛
* 注意：文件大小过大（1.2MB）

### 疫情数据

* 数据来源: https://news.163.com/special/epidemic/
* 数据日期: 2020-01-30 20:50

直接使用原始实现[首页代码](view-source:http://news.163.com/special/epidemic/)内的数据，包含截至日期的各城市的疫情数据`window.epidemic`，及1月20日至截至日期的每天的汇总疫情数据`window.data_by_date`，另额外添加了`window.bydate`来表示数据截至时间。

将这份数据截取下来，保存为[data.js](data/data/js)，供实现加载。

## 问题

* 最小代码原始实现完成，但是地图上的省份标识的位置与原始不符，原始的位置更合理。猜测网易团队将echarts地图数据`china.js`做过调整，待验证。原始实现的`china.js`代码在`https://static.ws.126.net/163/f2e/news/virus_report/static/js/main.97e1d1a6.js`，不太容易摘出。
