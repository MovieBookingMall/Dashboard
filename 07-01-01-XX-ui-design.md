UI Design
=========

（一）逻辑设计思路如下
----------------------

### 1.请求主页

>   URL：/index

>   返回结果：票多多主页

>   具体介绍：观影者准备购票时，首先进入票多多首页,包含正在热映电影和最近热门电影两个目录，观影者可以根据他们的喜好选择电影，或者在上方搜索框中查找他们想看的电影，并点击该电影下方的选座购票按钮可以进入电影详情界面；

![](https://github.com/MovieBookingMall/Dashboard/blob/master/images/01-1.png)

### 2.请求选择影院页面

>   URL：/cinemaSelection

>   返回结果：选择影院页面

>   具体介绍：进入该电影详情页面后，观影者可以看到该电影的分类，上映时间，用户评分以及票房等等，并可以选择观影日期，观影场所，所属地区，以及是否选择特殊厅以获得最佳观影体验；根据观影者的选择，票多多将符合选项的影院列入了影院列表中，观影者根据喜好选择影院列表中的场所，并点击右边的选座购票按钮，进入影院信息介绍界面；

![](https://github.com/MovieBookingMall/Dashboard/blob/master/images/01-2.png)

### 3.请求影院信息页面

>   URL：/cinemaInfo

>   返回结果：电影院信息主页

>   具体介绍:：进入影院信息介绍界面后，可以看到影院的具体位置，地图，以及影院提供的服务，该影院在上映的其他电影，观影者可以选择具体的放映时间，并点击选座购票按钮进入选座界面；

![](https://github.com/MovieBookingMall/Dashboard/blob/master/images/01-3.png)

### 4.请求选座页面

>   URL：/selectSeat

>   返回结果：选择座位页面

>   具体介绍：进入选座界面后，观影者可以根据具体的二维座位平面图，选择他们观影的座位

![](https://github.com/MovieBookingMall/Dashboard/blob/master/images/01-4.png)

### 5.支付页面

>   URL：/alipay

>   返回结果：支付页面

>   具体介绍：选座完成后，跳转至第三方支付界面

![](https://github.com/MovieBookingMall/Dashboard/blob/master/images/01-5.png)

### 6.请求登陆页面

>   URL：/loginPage

>   返回结果：登陆页面

>   具体介绍：用户可以在任意界面选择登陆，若选座完成后，用户仍未登陆，则系统会在其点击“确认选座”按钮时跳转至登陆界面

![](https://github.com/MovieBookingMall/Dashboard/blob/master/images/login.png)

（二）组件设计思路
------------------

### 1.图片

>   影片的图片都统一长宽比，给观影者提供很好的视觉效果

### 2.细节

>   电影、影院等信息都以列表的方式进行处理，使观影者有良好的购物体验
