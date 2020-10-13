# Analysis of consumer behavior

首先读取数据，如果是xlxs文件需要注意解码的问题，这里我读取的是txt文件格式。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/01.png)
为表赋予表头，查看一下该数据的前五项。数据是用户购买CD的明细，一共有用户ID(user_id)，购买日期(user_dt)，购买金额(user_products)，购买数量(user_amount)四个字段。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/02.png)
生成对数据的描述性统计。用户平均每笔订单购买2.6个商品，标准差在2.0，稍稍具有波动性。中位数在2个商品，75分位数在3个商品，说明绝大部分订单的购买量都不多。最多的用户购买了10个。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/03.png)
每位用户购买的数量以及所消费的金额。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/04.png)
根据每位用户的购买情况生成描述性信息。从用户角度看，每位用户平均购买8张CD，最多的用户购买了29张，属于狂热用户了。用户的平均消费金额（客单价）104元，标准差是95240，结合分位数和最大值看，平均值才和75分位接近，肯定存在小部分的高额消费用户。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/05.png)
按月统计每个月的CD销量。从图中可以看到，前两个月的销量非常高。数据比较异常。而后期的销量则很平稳。或许是CD刚发售热卖，也或许是公司的促销活动。之后比较平稳，或许是该CD的热度已过，有较平稳的波动。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/06.png)
绘制每笔订单的散点图。从图中观察，订单消费金额和订单商品量呈规律性，每个商品两元左右。订单的极值较少，超出80的就几个。显然不是异常波动的罪魁祸首。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/07.png)
绘制用户的散点图，用户也比较健康，而且规律性比订单更强。这是CD网站的销售情况，商品单一，金额和商品销售量基本成线性关系。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/08.png)
根据用户的消费金额和购买量生成直方图。可以发现高消费的用户较少，消费主力基本上还是集中在低消费的人群上。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/09.png)
计算用户消费的时间节点，用户第一次消费都在1997年的一月。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/10.png)
生成数据透视

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/11.png)
将数据转换一下，消费两次及以上记为1，消费一次记为0，没有消费记为NaN。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/12.png)
用sum和count相除即可计算出复购率。同时排除未消费的用户。count不论0还是1都会统计，所以是总的消费用户数，而sum求和计算了两次以上的消费用户。从图中看书，新用户的复购率大概在20%，在中期却有非常高的复购率,甚至一度达到了100%，后期的复购率基本为0。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/13.png)
将消费金额进行数据透视

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/14.png)
简化表格的内容，有过购买记为1，反之记为0。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/15.png)
新建一个判读函数，如果用户本月且下月都消费过记为1；用户本月消费，下月未消费记为0；本月未消费记为NaN。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/16.png)
计算用户的回购率。用户的回购率波动比较大。新用户的回购率在10%，老用户最高到了65%。
综合分析复购率和回购率，大多都集中在相同的时间段内。新客的整体质量低于老客，老客的忠诚度较好。但是波动的较大的原因有待进一步分析。

![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/17.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/18.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/19.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/20.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/21.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/22.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/23.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/24.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/25.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/26.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/27.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/28.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/29.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/30.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/31.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/32.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/33.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/34.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/35.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/36.png)
![image](https://github.com/Athrun-Judah/-pyhton-/blob/main/cdnew_image/37.png)

