---
title: background-color与background-imgage的区别
date: 2017-09-08 15:17:13
tags:
type: "CSS3"
---
先上一张图，这是从《图解CSS3核心技术与案例实战》上截下来的，文字内容比较多，因此就不逐一敲下来了。


这段话比较长，平时工作的时候也没有遇到过类似的问题，但是拿来研究下还是很有必要的。好了，闲话结束，代码加效果图奉上。
html代码：
``` bash
<body>
        <div id="cat"><p>content从这里开始</p></div>
    </body>
``` bash
1、正常效果图：                                  css代码：
                    

2、将div的border颜色改为透明，发现背景色红色的显示区域把边框也变为红色：
                  

由1、2可知，元素设置padding对背景色的显示无影响。

3、背景色换为背景图，左边的divborder颜色为橘黄色，右边的border颜色为透明：
                 
由3可知，背景色换为背景图显示效果与背景色一致。

4、我们知道，background默认重复方式为repeat，那么，如果设置为no-repeat，显示效果又会是怎样的呢。
4.1、背景色no-repeat且边框不透明时：           背景色no-repeat且边框透明时：
                  
4.2、背景图no-repeat且边框不透明时：            背景图no-repeat且边框透明时：
                        
由4.1可知，背景色在两种重复方式中表现一致，都与元素padding无关，都是从边框处开始铺展，border设置为透明即可验证。
背景图就比较有意思了，4.2中左图的呈现方式与repeat时一致（只是方式，不是最终效果哈），都是从元素padding外侧开始铺展。
4.2右图最外侧有一条额外的黑线，这是额外设置的outline，只是为了更好的显示效果，对我们今天的话题没有任何其他的影响。我们可以看到很有趣的现象，背景图此时并没有像3中右图那样从边框外侧开始铺展，而是与4.2左图一样从元素padding外侧开始铺展。

5、由4.2延伸出来的话题是关于background-position的，默认值是0 0，此处我们统一设置为10px 10px，来看下上述场景下这个属性又有哪些意想不到的效果。
                    
                   4.2                                                                      4.1
由上图可知，background-position在背景图不重复的时候起始点是从元素padding外侧开始定位的。
背景图重复的时候，background-position设置了也没有什么作用，因此也就没有讨论的必要性了。

规则比较有趣，但是说到实用性，我觉得在实际运用中，除非是比较特别的效果，不然是很少，很难去运用的。怎么说呢，增长下自身的知识深度，兴趣使然，无他。


































