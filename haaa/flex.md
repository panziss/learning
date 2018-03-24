一定要加浏览器前缀
注意，设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效。

# 以下6个属性设置在盒子上。 #

    flex-direction
    .box {
      flex-direction: row | row-reverse | column | column-reverse;
      //水平，起点左/水平，起点右/垂直，上到下/垂直，下到上
    }

    flex-wrap
    .box{
      flex-wrap: nowrap | wrap | wrap-reverse;//不换行/换行，第一行在上面/换行第一行在下面
    }

    flex-flow：属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。
    .box {
      flex-flow: <flex-direction> || <flex-wrap>;//flex-flow:排列方式 是否换行;
    }

    justify-content：属性定义了项目在主轴上的对齐方式。
    .box {
      justify-content: flex-start | flex-end | center | space-between | space-around;
    //左对齐/右对齐/居中/两端/平均分配左右的空，多用于做导航菜单
    }

    align-items：属性定义项目在交叉轴上如何对齐。
    .box {
      align-items: flex-start | flex-end | center | baseline | stretch;
    }

    align-content：属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。
    .box {
      align-content: flex-start | flex-end | center | space-between | space-around | stretch;
    }


# 以下6个属性设置在内容上。 #

    order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
    .item {
      order: <integer>;
    }

    flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
    .item {
      flex-grow: <number>; /* default 0 */
    }

    flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
    .item {
      flex-shrink: <number>; /* default 1 */
    }

    flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。
    浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
    .item {
      flex-basis: <length> | auto; /* default auto */
    }

    flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。
    .item {
      flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
    //该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)
    }

    align-self
    .item {
      align-self: auto | flex-start | flex-end | center | baseline | stretch;
    }




- 以块级元素显示（从上到下）：flex-direction:column;
- 让多个子元素在一行显示：flex-grow:1;
- 元素内容对齐方式：justify-content:center;

# flex #
    .item {
	  flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
	}

----------
# 子元素属性 #
    .item{
		order: <integer>;
		/*排序：数值越小，越排前，默认为0*/
		
		flex-grow: <number>; /* default 0 */
		/*放大：默认0（即如果有剩余空间也不放大，值为1则放大，2是1的双倍大小，以此类推）*/
		
		flex-shrink: <number>; /* default 1 */
		/*缩小：默认1（如果空间不足则会缩小，值为0不缩小）*/
		
		flex-basis: <length> | auto; /* default auto */
		/*固定大小：默认为0，可以设置px值，也可以设置百分比大小*/
		
		flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
		/*flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto，*/
		
		align-self: auto | flex-start | flex-end | center | baseline | stretch;
		/*单独对齐方式：自动（默认） | 顶部对齐 | 底部对齐 | 居中对齐 | 上下对齐并铺满 | 文本基线对齐*/
	}

# 容器样式 #
    .box{
	    flex-direction: row | row-reverse | column | column-reverse;
	    /*主轴方向：左到右（默认） | 右到左 | 上到下 | 下到上*/
	    
	    flex-wrap: nowrap | wrap | wrap-reverse;
	    /*换行：不换行（默认） | 换行 | 换行并第一行在下方*/
	    
	    flex-flow: <flex-direction> || <flex-wrap>;
	    /*主轴方向和换行简写*/
	    
	    justify-content: flex-start | flex-end | center | space-between | space-around;
	    /*主轴对齐方式：左对齐（默认） | 右对齐 | 居中对齐 | 两端对齐 | 平均分布*/
	    
	    align-items: flex-start | flex-end | center | baseline | stretch;
	    /*交叉轴对齐方式：顶部对齐（默认） | 底部对齐 | 居中对齐 | 上下对齐并铺满 | 文本基线对齐*/
	    
	    align-content: flex-start | flex-end | center | space-between | space-around | stretch;
	    /*多主轴对齐：顶部对齐（默认） | 底部对齐 | 居中对齐 | 上下对齐并铺满 | 上下平均分布*/
    }

# 定义容器的display属性 #
    .box{
		display: -webkit-flex; /*webkit*/
		display: flex;
		}
		
		/*行内flex*/
		.box{
		display: -webkit-inline-flex; /*webkit*/
		display:inline-flex;
	}


    justify-content: center 实现水平居中
	align-items: center 实现垂直居中。
	设置换行而不伸展：
	