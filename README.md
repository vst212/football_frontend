# football_frontend

一个自己写的竞彩足彩预测代码，通过大数据匹配亚盘历史相同赔率相同水位的比赛，来得出赢盘或者输盘的结果。目前持续测试中。

**请在issues中提交不准确的联赛和具体场次，以便我更新算法**

体验网址：[http://47.99.134.39:8080/](http://47.99.134.39:8080/)

#### 战绩统计

| 比赛类别        | 比赛时间            | 主队    | 比分  | 客队   | 分析              | 投注      | 概率     | 结果 |
|-------------|-----------------|-------|-----|------|-----------------|---------|--------|----|
| 23/24澳超第7轮  | 2023/12/8 18:45 | 珀斯光荣  | 1:2 | 墨尔本城 | 亚盘全网匹配赢16场,输26场 | 客队-0.75 | 61.90% | 红  |
| 22/23德乙第16轮 | 2023/12/9 20:00 | 凯泽斯劳滕 | 1:2 | 柏林赫塔 | 大小球全网大6场,小1场    | 大2.75   | 85.71% | 红  |


请作者吃碗沙茶面

<img width="400" height="600" src="./src/assets/images/alipay.jpg" alt="">


#### 使用手册

以23/24英超第15轮卢顿主场对阵阿森纳为例，比赛分析结果如下图：

![image](https://github.com/czl0325/football_frontend/assets/2100549/c69f0862-9270-4332-88e7-283a7d7eb89f)

可以看到欧赔指向阿森纳100%概率胜，但是亚盘卢顿+1.75有100%的概率赢盘，可以确认阿森纳能赢球，但是最多赢一个，赢不到2个，亚盘可以投注卢顿+1.75赢。而大小球指向大球100%的概率，所以本场买**阿森纳胜+卢顿1.75赢+2.75大球，全中**。
