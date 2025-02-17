# 红楼梦与语言统计学

红楼遗梦——红楼梦作者有谁？胡适的前80后40之说是否正确？

1987年，复旦大学李贤平教授的一篇《〈红楼梦〉成书新说》[1] 以一个全新的视角震动了红学界。其时作者自述用UWMadison的硬软件设备分析数月，当今俺花一天时间在pc上简单复现了文中的成果。

为了获取高质量的文本，最后选择了直接爬取“红楼星语”网站。我以庚辰本（北大脂批本）作1-80回，81-120采用程乙本。（庚辰本1718未分回，李文中对半拆开）

![](scatterplot.png)

*P1 以120回每回作为观测数据，以44个虚词和句长为特征，对应变换后在主平面的投影*

![](clustering.png)

*P2 以类卡方距离度量，类平均法递归的系统聚类图*

与 [1] 给出的主要论据“正视图”“聚类图”基本一致。可以看到两部分点有明显的分隔——前80回与后40回很可能出自截然不同的手笔。

争议极大的1-5回（“曹第五次批阅说”）、17-18回、53回都得到了一定的支持。

细分来看前80与后40均非浑然一体，李文还给出了许多激进的论断：前80由佚名《石头记》经曹雪芹《风月宝鉴》插入；及三次增删的具体回目；后40并非胡适所说高鹗一人而由曹家据遗稿补写，程刊高校而成；但同时回避了脂砚斋、曹頫等说的疑问。其后对此文章观点、方法论讨论不少。

**reference**

[1] 李贤平. (1987). 《红楼梦》成书新说. Fu Dan Xue Bao. She Hui Ke Xue Ban, (5), 3-16.

[2] 施建军. (2010). 关于以《红楼梦》120回为样本进行其作者聚类分析的可信度问题研究. Hong Lou Meng Xue Kan, (5), 318-335.

[3] 潘旭澜. (1987). 序《成书新说》. Fu Dan Xue Bao. She Hui Ke Xue Ban, (5), 17-18.

[4] 碧峰. (1988). 《〈红楼梦〉成书新探》讨论会简述. Fu Dan Xue Bao. She Hui Ke Xue Ban, (1), 111-112.

---

下载链接：

{download}`红楼梦文本 <./text.zip>`（网站文本、电子书转换的较脏文本，包含庚辰本、程乙本、当代校注本、脂评汇校本）

{download}`处理代码 <./code.zip>`（*Python*，包括爬虫、分析、变量数据）
