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



