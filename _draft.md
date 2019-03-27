## 公式设置

Writing LATEX: $\lim_{x \to \infty} \exp(-x)=0​$















## 图片设置

#### 图片位置-居左/居中/居右

图片

利用markdown在编写文档时插入图片是默认靠左，有些时候将图片设置为居中时可以更加的美观，这时就需要在图片的信息前边添加如下程序

<div align=center>![img](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1553656827307&di=36aeda6511f91f15a20876f81ddf6873&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fblog%2F201308%2F30%2F20130830162506_kmfuy.thumb.100_100_c.gif)


    <div align=center>![](http://xx.xx.xx)





​											图片





#### 如果想将图片位于右侧，只需要将center改为right

<div align=right>![这里写图片描述](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1553656827307&di=36aeda6511f91f15a20876f81ddf6873&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fblog%2F201308%2F30%2F20130830162506_kmfuy.thumb.100_100_c.gif)


    1<div align=right>![](http://xx.xx.xx)



#### 图片大小



    1<img src="http:..." width = "100" height = "100" div align=right />



如上格式，在图片的最后添加 width = “100” height = “100”，就可以设置图片的大小。也可以在后边输入百分比为多少，如 width = 20% height = 20%

```html
<img src="http:..." width = 30% height = 30% />
```



作者：泉伟 
来源：CSDN 
原文：https://blog.csdn.net/qq_35451572/article/details/79443467 
版权声明：本文为博主原创文章，转载请附上博文链接！
