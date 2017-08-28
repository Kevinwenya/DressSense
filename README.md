# DressSense
如何实现智能的服装搭配，比如我买了一件牛仔上衣，搭配什么样的下衣、鞋子好看尼

https://tianchi.aliyun.com/competition/introduction.htm?spm=5176.100067.5678.1.7c560628ocZghW&raceId=231506

描述：穿衣搭配是服饰鞋包导购中非常重要的课题，它所延伸出的技术、算法能广泛应用到大数据营销几乎所有场景中，如搜索、推荐和营销服务。淘宝穿衣搭配算法竞赛将为参赛者提供搭配专家和达人生成的搭配组合数据，百万级别的淘宝商品的文本和图像数据，同时还将提供用户的脱敏行为数据。期待参赛者能从以上行为、文本和图像数据中挖掘穿衣搭配模型，为用户提供个性化、优质的、专业的穿衣搭配方案。

给的数据集有4部分、达人搭配组合、商品信息、购买记录、线上测试集，主要从下述两方面考虑

一，计算商品间的相似度，选择最相似的200个商品作为搭配；
1)        利用商品全集的标题建立词袋（bag-of-words)并计算每个商品的TF-IDF向量。
2)        利用达人搭配列表找出相互搭配的搭配类目组合。
3)        利用TF-IDF向量找出待搭配商品最相似的500个商品得到500个商品对。
4)        500个商品对对应着500个类目对，剔除不在搭配类目组合中的类目对
5)        排序，取Top 200个

二，从用户购买历史中，选择最经常被用户同时购买的商品组合进行搭配
核心就是统计2个商品被多少个用户同时买过，然后按用户数量从高到低排序，取Top 200

