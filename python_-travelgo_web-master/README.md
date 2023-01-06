# Python期末项目——Travelgo!  
### - Python+flask+pythonanywhere实现网站设计 -   
- 前排提示，功能页的加载可能相对较慢，如果不动了直接点左上角的停止加载，一般都能出现页面。  
- **而且几乎每个页面都有图片，图片较大，特别是头像图，因为是动图的关系，需要等待加载！不是加载失败！谢谢各位观众老爷了**！！！！
---
## 一、项目概况  
#### 1. 本项目名：Travelgo[Python+Flask Web] 
- 名为**Travelgo!** ，使用了python和flask的功能，致力于在广大年轻的用户打算去某地区进行旅游前提供一个能够快速且便捷地提供**规划出行计划**建议和参考的网站。   
#### 2. 价值主张宣言：   
- **针对广大用户旅行前对旅行目的地不熟悉、对当地天气不了解的痛点**——我们网站调用了几类用户常用的路径查找和天气查询的api接口，将这些功能集合在同一个网页，以便于用户在做旅游攻略时**不必更换不同app进行查找**，从而提高准备出行出行计划的**效率**。  
- 同时，网站对与相信星座的用户有一定吸引力，登陆时输入星座即可查看**星座运势**  
- 以人为本，从用户痛点出发进行功能构建。

#### 3. 功能框架结构图展示：    
> ![功能框架结构图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/gongnengjiegouliuchengtu.jpg)    

---  

## 二、问题描述  

#### 1. 主要痛点：  
- 广大用户旅行前对旅行目的地不熟悉、对当地天气不了解。而在大数据发展的时代下，网上可供参考的信息五花八门，且通常呈现**多样又分散**的特点，对用户在整合信息进行计划规划无疑是一大烦恼。 

#### 2. 用户画像：
- 我们针对的用户主要是希望去旅游，但是不擅长/不方便做旅游规划的用户。
- 针对他们不熟悉、耐心相对较低或不了解情况的特征，挑选了几份大致的用户画像。
> ![用户1](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E7%94%A8%E6%88%B7%E7%94%BB%E5%83%8F1.jpg)  
- 应用场景：针对这一情况，阿明能利用travelgo直接一个网站搜索到大部分想要的信息，不用翻各种网站才得到结果

> ![用户2](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E7%94%A8%E6%88%B7%E7%94%BB%E5%83%8F2.png)    
- 应用场景：针对这一情况，小瓜在travelgo登陆后即可获得星座运势占卜的功能解决了烦恼，同时还能结合天气+路径的查找，满足星座之旅的愿望。

> ![用户3](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E7%94%A8%E6%88%B7%E7%94%BB%E5%83%8F3.png)  
- 应用场景：针对这一情况，卡卡能利用travelgo直接一个网站搜索到大部分想要的信息，不用因为粉丝情况不同而辗转到各个网页进行信息搜寻再返还给粉丝。
#### 3. 价值主张画布：  
> ![价值主张画布](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E4%BB%B7%E5%80%BC%E4%B8%BB%E5%BC%A0%E7%94%BB%E5%B8%83.jpg)
- 根据价值主张画布的指引，并针对客户痛点，Travelgo整合了各api接口，服务于用户的旅游计划规划和撰写分享。具体传递程序都在图中所示，颜色互相对应，这边就不详细展开了。  

---  

## 三、解决方案描述  

#### 1. Python下的整体项目规划  
- 运用了python+flask的模式，从高德API和极速数据API中调用接口，实现了在同一页面的功能实现，既可以查询各类型的天气，也能获取适合的路线推荐，同时还能让用户进行星座运势查询
> ![功能页](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%8A%9F%E8%83%BD%E9%A1%B5.png)  

#### <mark>思维导图辅助理解</mark>  
- 利用python**函数**的功能，定义了天气查询返回不同类型值的函数，以及路径步行、自驾、骑行路径规划查询的函数；  
- 利用form+action以及onclick的方法，让用户填入一次信息传送到不同的结果页面，方便快捷，不用跳转不同网站寻找想要的数据
- 同时利用了**列表和字典切片和提取**的方法，使得返回的数据更加简洁，方便用户查看；  
- 在用户日志系统页面，使用了**for循环**，快速将提取到的数据装入列表，方便查看访客使用记录。
>![思维导图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E6%80%9D%E7%BB%B4%E5%AF%BC%E5%9B%BE.png)  

#### 2. 项目页面流程图  
- 查询页面没有全部放出来，因为样式相似，避免重复，仅提供一个参考，实际页面数量参考框架图或网页。
> ![页面流程图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E9%A1%B5%E9%9D%A2%E6%B5%81%E7%A8%8B%E5%9B%BE_%E7%94%BB%E6%9D%BF%201.png)

#### 3. 结合API实现项目的智能加值
优先需求 | 需求 | 智能加值 | API类型 | 优先级 | 
---|---|---|---|---
了解旅游日的天气 | 不了解目的地的天气 | 是 | 高德API天气查询|A（非常重要）
布署到目的地路线 | 不了解如何到达目的地 | 是 | 高德AIP步行规划、驾车规划、骑行规划|A（非常重要）
了解自己的运气 | 想查看今日运势并与旅游计划相结合 | 是 |极速数据API星座运势查询|B（一般重要）  

---  

## 四、编程功能基本描述  
#### 1. 具体实践的思路：  
- 学习如何使用flask，可以根据实际情况选择参考链接进行自我学习，链接很详细：  
1、[初识flask，搭建第一个自己的网页](https://zhuanlan.zhihu.com/p/73278003)；  
2、[Flask 10天开发一个网站](https://zhuanlan.zhihu.com/p/33038507)  
3、[W3C的flask教程](https://www.w3cschool.cn/flask/)
- 做项目时首先思考用户的痛点以及现有的API接口，寻找切合的接口将其联系起来，构建起一个整体的思想框架，利用类似process on的软件建立思维导图，理清思路后使用python**函数定义**的方式逐一进行功能的实现。函数返回结果需要结合需求去取参数，这就要求我们熟练掌握**列表**、**字典**等结构。注意结构层次，不知道具体操作可以直接百度问题，一般都会有解答。可以在ipynb文档中尝试后再加入函数页面，不易出错。  
- **优化css时**，选择使用浏览器的**检查**功能，直接修改css样式，能够更加快速看见样式的变化，也不怕浏览器因为cookie缓存而不能及时反馈最新的样式。
- **数据传输**方面，注意不同类型文件的**摆放位置**。基本就是templates文件夹的html页面用外部链接static文件下css文件，py文件复制写具体文字内容并通过<mark>{{数据名字}}</mark>的方式进行传输。 
- **云端部署方面**，以文件压缩的方式上传，并上传到mysite里，上传前检查好代码是否全部正常运行，否则在云端处理非常麻烦。
- 项目需要掌握**知识结构比**例：列表、字典、函数等python技能占60%、数据传输流程了解占20%，文件处理占10%、云端部署占10%

#### 2. 后端数据传输流程图演示：  
> ![后端数据流程图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%90%8E%E7%AB%AF%E6%95%B0%E6%8D%AE%E4%BC%A0%E8%BE%93.jpg)
#### 3. 遇bug经验分享：
  1. 如果外部引入**css不显示**可能是html页面的<!Doctype html>作怪，删除即可成功引用；  
  当然，也可能是你服务器缓存cookie作怪，一般去删除浏览记录就可以了。  
  **具体参考：[[Python] 用Flask引入CSS无法正常显示](https://blog.csdn.net/u012358474/article/details/49968355)**
  2. 如果使用外部icon不成功，可以到根目录修改。  
  **具体参考:[[Django]实现html页面中 "GET /favicon.ico HTTP/1.1" 404报错](https://blog.csdn.net/ainivip/article/details/85597213)**  
  3. 如果import你想要的模块变灰，可以点开file找到make dictionary as再点击source root，再去点击import那一行代码的小灯泡的最后一行即可修复。  
  **具体参考：[[Pycharm]中import导入包呈现灰色问题之解决！](https://blog.csdn.net/pythonxiaohei/article/details/99698027)**
  4. 云端部署方面：
      1. 如果你的网站有api接口的调用，要记得给pythonanywhere发送反馈，向他们提供api文档网址，**是文档地址噢！不是接口地址！！**，有条件就不要加重别人的负担啦。  
      2. 如果缺失模块，可以选择到工作台进行安装。具体安装方式[参考链接：在pythonanywhere中手动安装模块并更改其位置](http://cn.voidcc.com/question/p-gxhbgzqp-qe.html)  
      3. 部署流程不熟悉，可参考链接：[PythonAnywhere部署Flask项目
](https://blog.csdn.net/qq_37935516/article/details/89165416)

---

## 五、云端项目部署基本描述  
#### 1. 总体页面结构图预览  
（<mark>总体页面以这张图或网站为准</mark>）  
> ![功能框架结构图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/gongnengjiegouliuchengtu.jpg)  

#### 2.首页及登录和注册  
- **页面流程图**  
> ![流程图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E9%A6%96%E9%A1%B5%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg)
- **功能介绍**：采用可翻转式卡片设计，在鼠标移动到卡片中央时可以发现登录及注册的入口。  
- [首页地址：http://shuimushisan.pythonanywhere.com/](http://shuimushisan.pythonanywhere.com/)  
> 首页及点击翻转卡片后![首页](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E9%A6%96%E9%A1%B5.png)  
![首页翻转](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E9%A6%96%E9%A1%B5%E7%BF%BB%E8%BD%AC.png) 
- [登录地址：http://shuimushisan.pythonanywhere.com/login](http://shuimushisan.pythonanywhere.com/login)  
> 登录![登录](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E7%99%BB%E5%BD%95.png)
- [注册地址：http://shuimushisan.pythonanywhere.com/setup](http://shuimushisan.pythonanywhere.com/setup)  
> 注册![注册](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E6%B3%A8%E5%86%8C.png)  

#### 3.功能页   
- 前排提示，功能页的加载可能相对较慢，如果不动了直接点左上角的停止加载，一般都能出现页面。  
- **而且图片较大，特别是头像图，因为是动图的关系，需要等待加载！不是加载失败！谢谢各位观众老爷了**！！！！
- **页面流程图**  
> ![流程图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%8A%9F%E8%83%BD%E9%A1%B5%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg)
- **功能介绍**：采用统一的导航栏，实现各种功能之间的快速跳转，跟住上面登录和注册填入的用户信息会调用不同api实现星座运势的输出。，点击相应按钮能进入相应的功能页。  
- [功能页地址：http://shuimushisan.pythonanywhere.com/homepage](http://shuimushisan.pythonanywhere.com/homepage)  
> ![功能页](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%8A%9F%E8%83%BD%E9%A1%B5.png) 

#### 4. 天气查询页  
- **页面流程图**  
> ![流程图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%A4%A9%E6%B0%94%E6%9F%A5%E8%AF%A2%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg)
- **功能介绍**：采用统一的导航栏，实现各种功能之间的快速跳转，调用了高德天气查询API，进行不同类型天气状况的查询。  
- [天气查询开屏：http://shuimushisan.pythonanywhere.com/homepage](http://shuimushisan.pythonanywhere.com/kaiping)  
> ![天气查询开屏](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%A4%A9%E6%B0%94%E5%BC%80%E5%B1%8F.png)  
- [天气查询：http://shuimushisan.pythonanywhere.com/tianqizhanbu](http://shuimushisan.pythonanywhere.com/tianqizhanbu)  
> ![天气查询](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%A4%A9%E6%B0%94%E6%9F%A5%E8%AF%A2.png)  
- 天气查询结果之一： 
> ![天气查询结果](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E5%A4%A9%E6%B0%94%E6%9F%A5%E8%AF%A2%E7%BB%93%E6%9E%9C%E4%B9%8B%E4%B8%80.png)   

#### 5. 路径查询页  
- **页面流程图**  
> ![流程图](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E8%B7%AF%E5%BE%84%E6%9F%A5%E8%AF%A2%E6%B5%81%E7%A8%8B%E5%9B%BE.jpg)
- **功能介绍**：采用统一的导航栏，实现各种功能之间的快速跳转，调用了三种高德路径查询API，进行不同类型路径规划的查询。  
- [路径查询开屏：http://shuimushisan.pythonanywhere.com/roadhome](http://shuimushisan.pythonanywhere.com/roadhome)  
> ![路径查询开屏](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E8%B7%AF%E5%BE%84%E6%9F%A5%E8%AF%A2%E5%BC%80%E5%B1%8F.png)  
- [路径查询：http://shuimushisan.pythonanywhere.com/road](http://shuimushisan.pythonanywhere.com/road)   
> ![路径查询](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E8%B7%AF%E5%BE%84%E6%9F%A5%E8%AF%A2.png)  
- 路径查询结果之一： 
> ![路径查询结果](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E8%B7%AF%E5%BE%84%E6%9F%A5%E8%AF%A2%E7%BB%93%E6%9E%9C%E4%B9%8B%E4%B8%80.png)   

#### 6. 用户日志系统  
- **功能介绍**：由导航栏进入，查看用户查询的数据以及返回的结果  
- [用户日志系统：http://shuimushisan.pythonanywhere.com/viewlog](http://shuimushisan.pythonanywhere.com/viewlog)
> ![用户日志系统](https://gitee.com/shuimushisan/python_-travelgo_web/raw/master/picture/%E6%97%A5%E5%BF%97%E7%B3%BB%E7%BB%9F.png)  
#### 7. 部署心得：  
- 部署过程很简单，其实就是确认代码完整无误后，将你的文件压缩打包上传到pythonanywhere，接着到工作台解压，并修改进入路径。  
- 注意要提前给工作人员发送反馈关于你在网站里调用的api接口**文档地址**  
- 如果报错，可以到报错日志查看错误原因，一般错误原因展示在最后一句。 
- 实在不懂可以参考链接：[PythonAnywhere部署Flask项目
](https://blog.csdn.net/weixin_45623528/article/details/105370431)
 

---

## 六、学习/实践心得总结及感谢  
#### 1. 学习心得：
- 这次的python期末项目，让我更加清楚地明白了数据传输的具体完整流程以及应该如何操作，以及页面之间跳转的标签如何设置——可以使用form表格+action标签提交。如果是一个数据传输到不同页面，也可以用onclick属性+js进行跳转。具体代码可查看：[知乎：js里的onclick事件怎么用？](https://zhuanlan.zhihu.com/p/139921524)  
- 同时也让我了解到了类似bootstrap的css框架网站，但是个人更喜欢用codepen里的框架，更多样灵活，也更易寻找。  
- 本次项目锻炼了我的**编程思维**，令我在建设网站时能够先构思大致框架，再将功能分成一个个小部分逐个击破，**提高了我的完成效率**，最终呈现出这一版的Travelgo!
#### 2. 感谢开源数据作者  
本次项目的样式以及代码撰写有参考了很多作者的开源代码，在此罗列并表示我由衷的感谢！也希望我提供的地址能够让更多人认识这些优秀的作者！  
</br>
**1. 基本框架**：
  - 首先是bootstrap官网的基本框架：[bootstrap](https://www.bootcss.com/)  
  - 以及bootstrap教程视频：[极客学院：一周学会Bootstrap](https://www.bilibili.com/video/BV1Lx411v73k?from=search&seid=16610645895972569308)   

**2. 一些codepen的零碎控件**：  
   - [导航栏基本样式参考](https://codepen.io/Pawan_Sharma46/pen/qBNdYyo)  
   - [路径开屏svg动画参考](https://codepen.io/yungtiec/pen/qNjPwr)  
   - [天气开屏svg动画参考](https://codepen.io/motorlatitude/pen/CyqDf)  
   - [表格样式参考](https://codepen.io/heypablete/pen/qdIsm)  
  
**3. b站技术指导**：
   - b站up技术指导（这个up注释很棒！还提供开源代码以及演示地址，很适合小白学习）：[阿阳爱前端](https://space.bilibili.com/478490349/)  
   - 菜鸟教程技术指导：[菜鸟教程](https://www.runoob.com/)  
   - b站：[注册登录等干货指导](https://www.bilibili.com/video/BV1jx411R73z?from=search&seid=10507059144201705707)
     
**4. API接口提供**：  
   - [高德API](https://lbs.amap.com/);  
   - [极速数据](https://www.jisuapi.com/)  
---  
>全文外联url链接共20个；  
原创图表共12个：[链接仓库](https://gitee.com/shuimushisan/python_-travelgo_web/tree/master/picture)


 