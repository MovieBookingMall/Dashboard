# 接口说明
本文档详细说明了后端暴露给前端调用的接口，包括调用接口的方法，请求参数和返回结果等详细信息。

## （一）页面请求接口
### 1.请求主页接口
URL：/index  
请求方法：GET  
参数：（无）  
返回结果：票多多主页  


### 2. 请求选择影院页面接口
URL：/cinemaSelection  
请求方法：GET  
参数：（无）  
返回结果：选择影院页面  

### 3. 请求影院信息页面接口
URL：/cinemaInfo  
请求方法：GET  
参数：（无）  
返回结果：电影院信息主页  

### 4. 请求选座页面接口
URL：/selectSeat  
请求方法：GET  
参数：（无）  
返回结果：选择座位页面  

### 5. 请求登陆页面接口
URL：/loginPage  
请求方法：GET  
参数：（无） 
返回结果：登陆页面  

## （二）用户操作接口
### 1. 获取用户信息接口
URL：/user/{id}  
请求方法：GET  
参数：用户ID，INT类型  
返回结果：与用户ID相同的用户信息，Json格式  
例子：  
request: /user/23  
response: {id:23, name:张三, sex:1, age:19}

### 2.用户注册接口
URL：/user/register  
请求方法：POST  
参数：注册用户信息  
返回结果：注册结果，String类型  
例子：  
request：/user/register  
附带数据：{name:张三, sex:1, age:19, account: "zhangsan123", password:"123456"}  
response：success  

### 3. 用户登录接口
URL：/user/login  
请求方法：POST  
参数：{account: "账户名"，password:"密码"}  
返回结果：登录结果  
例子：  
request: /user/login  
附带数据：{account: "zhangsan123"，password:"123456"}  
返回结果：success  

## （三）推荐系统接口
### 1. 推荐接口
URL：/doRecommend  
请求方法：POST  
参数：目标用户ID，INT类型  
返回结果：当前登录用户与目标用户的相似度  
例子：  
request：/doRecommend  
附带数据：{ID：9}  
返回结果：5.46  
