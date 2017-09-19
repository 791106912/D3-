# 初识D3 #
## 一、基础API和概念 ##
### 1、比例尺 ###
#### 数值比例尺 ####
什么是线性尺寸，在我的理解中就是一次函数。    
d3.scale.identity -构建一个线性恒等比例尺
d3.scale.ordinal() - 构建一个序数比例尺

	var xScale = d3.scale.ordinal()
			.domain(d3.range(5)) //定义输入域
		    .rangeRoundBands([0,10]);//指定输出范围为连续区间，区间段的起点均为整数。

##### 坐标轴 #####

	d3.svg.axis();//创建一个默认的轴

	axis.scale参数设置刻度尺，并返回轴，如果没有设定scale参数，将返回当前的刻度尺，默认为线性刻度
## 二、重要之布局 ##
### 前言 ###
什么是布局     
   
   简单的来说：可以把它理解为制作常见图形的函数，他的作用就是根据你
的原始数据去生成符合你要作图的。     
   D3总共提供了12个布局。饼状图（Pie）、力导向图(Focus)、弦图（Chord）、树状图（）、集群图（）、捆图（）、打包图（）、直方图（）、分区图（）、堆栈图（）、矩阵树图（）、层级图（）。
### 1、分区布局 ###

	var a = d3.layout.partition();//
	//默认为值降序的排序；
	//默认值的访问器假定为每一个输入值中一个带有数值属性的对象。
	//默认子值的访问器为每一个输入值的一个带有数组属性的对象
	
首先是partition.nodes(root)  
   返回指定根节点root的相关联的节点矩阵数组。	

	var nodes = a.nodes（data）
	console.log(nodes)
	//children:Array(4)  //子节点的矩阵数组
	  depth:0   //节点的层级数，根节点为0
	  dx:500
	  dy:125
	  name:"中国"
	  value:19  //该节点的值，值访问器返回得值
	  x:0   //节点位置的最小x坐标
	  y:0   //节点位置的最小y坐标
	  __proto__:Object
	
下面就是

	var link = a.link(nodes);
	console.log(link);
	
### 三、事件 ###

	d3.event

	d3.mouse(container)
	//返回当前d3.event相对于指定容器的x和y坐标
