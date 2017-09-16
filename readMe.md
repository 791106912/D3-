#初识D3
##一、基础API和概念
###1、比例尺
####数值比例尺
什么是线性尺寸，在我的理解中就是一次函数。    
d3.scale.identity -构建一个线性恒等比例尺
d3.scale.ordinal() - 构建一个序数比例尺

	var xScale = d3.scale.ordinal()
			.domain(d3.range(5)) //定义输入域
		    .rangeRoundBands([0,10]);//指定输出范围为连续区间，区间段的起点均为整数。

#####坐标轴

	d3.svg.axis();//创建一个默认的轴

	axis.scale参数设置刻度尺，并返回轴，如果没有设定scale参数，将返回当前的刻度尺，默认为线性刻度
##二、重要之布局
###前言
什么是布局     
   
   简单的来说：可以把它理解为制作常见图形的函数，他的作用就是根据你
的原始数据去生成符合你要作图的。     
   D3总共提供了12个布局。饼状图（Pie）、力导向图(Focus)、弦图（Chord）、树状图（）、集群图（）、捆图（）、打包图（）、直方图（）、分区图（）、堆栈图（）、矩阵树图（）、层级图（）。
###1、分区布局

	d3.layout.partition();



