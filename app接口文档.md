# app接口文档

## 示例：注册\(用户端\)

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_deals](http://API_DOMAIN/index.php?ctl=api_deals)

请求方式：GET

参 数：

* 分类id\(cate\_id\) 

返回状态：200（成功）

返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "name": "第三方",
            "limit_price": "63.00",
            "support_amount": "0.00",
            "begin_time": "1496886153",
            "end_time": "1498354957",
            "support_count": 0,
            "is_hot": 0,
            "is_special": 0,
            "user_name": "fanwe",
            "user_avatar": "http://www.zc.local.com/public/avatar/default/noavatar_7.JPG",
            "per": 0,
            "sur": 0
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

## 获取验证码

接口地址：[http://59.110.4.227:1005/captcha](http://59.110.4.227:1005/captcha)

请求方式：GET

参 数：

* 手机号\(phone\) 
* 类型\(type 注册时不传,忘记密码和修改密码时传 pwd\)

返回状态：200（成功）

返 回 值：

    {
    ```
    "status_code": 200,
    "message": "成功"
    ```
    }



