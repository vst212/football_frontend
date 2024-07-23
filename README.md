# football_frontend

一个自己写的竞彩足彩预测代码，通过大数据匹配亚盘历史相同赔率相同水位的比赛，来得出赢盘或者输盘的结果。目前持续测试中。

$\color{red}{👋👋👋热烈祝贺本项目2024欧洲杯完成仅错三场的战绩，成功杀庄。 👋👋👋}$

**本项目打法仅适用于滚球的亚盘和大小球，不适用于竞彩，（欧赔仅娱乐，准确率不高。）建议在开场后一分钟内查看分析最准确。（请注意，亚盘中的赢盘和输盘都是指主队。）**

#### 版本历史

* 2023-12-08 : 1.0版本 基础匹配功能
* 2024-01-26 : 1.1版本 增加设置和匹配详情参考
* 2024-02-01 : 1.2版本 增加亚盘的水位趋势图
* 2024-05-08 : 1.3.2版本 修改致命bug
* 2024-06-21 : 1.3.3版本 增加剔除偏差过大的水位，修复亚盘趋势的bug


体验网址：[点击跳转体验](http://106.54.58.139:8080/#/home)

#### 经典战役

[23/24葡超29轮波尔图vs法马利康，100%概率下盘](http://47.99.134.39:8080/#/match/detail?fid=1101833)<br>
[24秘鲁甲11轮加西拉索vs水晶体育，100%概率大球](http://47.99.134.39:8080/#/match/detail?fid=1136633)<br>
[24中超第24轮青岛西海岸vs梅州客家，100%概率下盘](http://106.54.58.139:8080/#/match/detail?fid=1134475)<br>

#### 分析思路

以23/24英超第22轮利物浦主场对阵切尔西为例，利物浦赛前排名第一，积分48，切尔西赛前排名第10，积分31，已知每家菠菜公司开出的初赔，初赔主队水位，客队水位，以及即时赔率，即时赔率主队水位，客队水位。<br>
通过大数据找出历史比赛中，初赔同样让球，主客队水位相同的比赛(误差±0.015)，即时赔率同样让球，主客队水位相同的比赛，如果是联赛，且联赛赛程已经超过1/4，因为利物浦排名比切尔西高，再加入筛选条件主队排名高于客队的比赛，以及主队积分>=客队积分+(48-31)的比赛，最终将找到的所有比赛计算赢盘输盘的场次，来得出赢盘输盘的概率。

#### 急需解决的问题

1. 需要加入状态对比，比如当前主队状态好，客队状态差，从赔率匹配到的数据中筛选出同样是主队状态好，客队状态差的比赛。（需要解决：如何确定当前主队状态是好还是差？）
2. 需要加入场均进球数对比，匹配历史同样的比赛中，主客队的场均进球数也大致一样的。

群聊二维码：

<img width="400" src="./src/assets/images/wx.jpg" alt="">


请作者吃碗沙茶面

<img width="400" height="600" src="./src/assets/images/alipay.jpg" alt="">


#### 使用手册

以23/24英超第15轮卢顿主场对阵阿森纳为例，比赛分析结果如下图：

![5121702605151](https://github.com/czl0325/football_frontend/assets/2100549/678869f7-3344-4ec9-900e-495b768b419f)



可以看到欧赔指向阿森纳100%概率胜，但是亚盘卢顿+1.75有100%的概率赢盘，可以确认阿森纳能赢球，但是最多赢一个，赢不到2个，亚盘可以投注卢顿+1.75赢。而大小球指向大球100%的概率，所以本场买**阿森纳胜+卢顿1.75赢+2.75大球，全中**。
