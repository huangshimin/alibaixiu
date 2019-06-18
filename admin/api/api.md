## 判断登录账号和密码是否正确的接口
type: post
url: api/doLogin.php
data:
    email：邮箱
    password:密码

响应体：
    JSON

    { "code":10000, "msg":"ok" }
    或者
    { "code":10001, "msg":"fail" }


## 判断有没有登录的接口
type:get
url: api/checkLogin.php
data:没有
响应体：
    JSON

    { "code":10000, "msg":"ok" }
    或者
    { "code":10001, "msg":"fail" }


## 获取当前登录的用户信息接口
type:get
url:api/getUserInfo.php
data:没有
响应体：
    JSON
    { "id":1,"slug":"admin",...... }


## 获取网站统计数据的接口
type:get
url:api/getWebInfo.php
data:没有
响应体：
    JSON
    {wenzhang:700  caogao:210  fenlei:4  pinglun:400  daishenhe:83}


## 获取分页评论数据的接口
type:get
url:api/getComments.php
data:
    pageIndex: 页码
    pageSize: 页容量

响应体：
    JSON
    {
        data:[
            {},
            {},
            {}
        ],
        totalPages:43
    }


## 修改评论状态的接口
type:post
url:api/editComments.php
data:
    status：告诉我要修改成什么状态
    ids： 告诉我要修改成哪些数据
            如果单行值传一个id，如果多行，就传多个id
            ids的取值要么是 “3" 这样的，要么就是 "3,9,10,11"这样的

响应体：
    JSON
    
    { "code":10000, "msg":"ok" }
    或者
    { "code":10001, "msg":"fail" }


## 获得文章的接口
type:get
url: api/getPosts.php
data:
    pageIndex:页码
    pageSize:页容量
    category:要筛选的分类
    status:要筛选的状态

响应体：
    JSON
    {
        data:[ {},{} ],
        totalPages:76
    }


## 获得所有分类的接口
type:get
url:api/getCategory.php
data:无
响应体：
    JSON
    [{},{},{},{}]