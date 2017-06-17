# app接口文档

## 说明：

* status\_code 返回状态码 200（成功） 400（失败）
* message 返回信息
* data 返回数据

---

* ### 众筹列表

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_deals](http://API_DOMAIN/index.php?ctl=api_deals)

请求方式：GET

参 数：

* 分类id\(cate\_id\) int 
* 页数\(page\) int

返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "name": "第三方", // 众筹项目名称
            "limit_price": "63.00", // 目标金额
            "support_amount": "0.00", // 已筹金额
            "begin_time": "1496886153", // 开始时间
            "end_time": "1498354957", // 结束时间
            "support_count": 0, // 支持人数
            "is_hot": 0, // 是否热门 0 否 1 是
            "is_special": 0, // 是否置顶 0 否 1 是
            "user_name": "fanwe", // 发起人名字
            "user_avatar": "http://www.zc.local.com/public/avatar/default/noavatar_7.JPG", // 发起人头像
            "per": 0, // 筹集金额百分比
            "sur": 0 // 剩余天数
        },
         {
            "name": "拥有自己的咖啡馆",
            "limit_price": "5000.00",
            "support_amount": "5500.00",
            "begin_time": "1351711495",
            "end_time": "1560367440",
            "support_count": "11",
            "is_hot": 0,
            "is_special": "1",
            "user_name": null,
            "user_avatar": "http://www.zc.local.com/public/avatar/default/noavatar_0.JPG",
            "per": 1,
            "sur": 0
        }
    ]
}
```
##

* ### 个人中心 个人设置页

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_user&act=index](http://API_DOMAIN/index.php?ctl=api_user&act=index)

请求方式：GET

参 数：

* 用户id/(id/_id\) int 

返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "19",
            "user_name": "test",
            "age": "20",
            "mobile": "123",
            "head": "/public/avatar/default/noavatar_9.JPG",
            "bank": "(尾号)"
        },
        [
            {
                "id": "21",
                "user_id": "19",
                "province": "北京",
                "city": "北京",
                "address": "亦庄",
                "mobile": "110",
                "zip": "",
                "consignee": "njw",
                "is_default": "0"
            },
            {
                "id": "22",
                "user_id": "19",
                "province": "北京",
                "city": "北京",
                "address": "亦庄",
                "mobile": "110",
                "zip": "",
                "consignee": "njw",
                "is_default": "1"
            }
        ]
    ]
}
```

## 

* ### 个人中心 修改年龄、电话

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_user&act=update](http://API_DOMAIN/index.php?ctl=api_user&act=update)

请求方式：GET

参 数：

* 用户id/(id/_id) int 
* 若修改年龄 age/（age/_age） int
* 若修改电话 mobile/(mobile/_mobile) int

返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": []
}
```

## 

* ### 个人中心 修改或添加收货地址

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_user&act=addressEdit](http://API_DOMAIN/index.php?ctl=api_user&act=addressEdit)

请求方式：GET

参 数：

* 用户id/(user_id/_user_id) int 
* 若修改 修改的地址的id id/（id/_id） int  若添加 不用传递地址id（id/_id）
* 收件人consignee/(consignee/_consignee) str
* 联系方式mobile/(mobile/_mobile) int
* 所在省地区province/(province/_province) str
* 所在市地区city/(city/_city) str
* 详细地址address/(address/_address) str
* 是否设为默认地址is_default(is_default/_value) int 0-不是默认；1-默认地址

返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": []
}
```

## 

* ### 我的关注列表

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_user&act=myFocus](http://API_DOMAIN/index.php?ctl=api_user&act=myFocus)

请求方式：GET

参 数：

* 用户id/(user_id/_user_id) int 
* 页数page/(page/_page) int 用于下拉加载

返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "58",
            "name": "流浪猫的家—爱天使公益咖啡馆的重建需要大家的力量！",
            "image": "./public/attachment/201211/07/11/438813e6d75cb84c6b0df8ffbad7aa8c31.jpg",
            "is_effect": "1",
            "begin_time": "1352145022",
            "end_time": "1497297000",
            "is_success": "1"
        }
    ]
}
```

## 

* ### 退出登录

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_user&act=loginout](http://API_DOMAIN/index.php?ctl=api_user&act=loginout)

请求方式：GET

参 数：


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": []
}
```

## 



