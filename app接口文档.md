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

---

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
            "id": "19", //用户id
            "user_name": "test", //用户名
            "age": "20", //用户年龄
            "mobile": "123", //用户手机号
            "head": "/public/avatar/default/noavatar_9.JPG", //用户头像地址
            "bank": "(尾号)" //用户银行账号
        },
        [
            {
                "id": "21", //收货地址id
                "user_id": "19", //用户id
                "province": "北京", //收货地址-省
                "city": "北京", //收货地址-市
                "address": "亦庄", //收货地址-详细地址
                "mobile": "110", //收货地址-收货人电话
                "zip": "", 
                "consignee": "njw", //收货地址-收货人姓名
                "is_default": "0" //收货地址-是否默认地址
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

---

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

---

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
            "id": "58", //项目id
            "name": "流浪猫的家—爱天使公益咖啡馆的重建需要大家的力量！", //项目标题
            "image": "./public/attachment/201211/07/11/438813e6d75cb84c6b0df8ffbad7aa8c31.jpg", //项目图片
            "is_effect": "1", //是否通过审核
            "begin_time": "1352145022", //项目开始实时间
            "end_time": "1497297000", //项目结束时间
            "is_success": "1" //是否集资成功
        }
    ]
}
```

---

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

---

* ### 获取众筹分类列表

接口地址：[http://API\_DOMAIN/index.php?ctl=api\_user&act=loginout](http://www.zc.local.com/index.php?ctl=api_deals&act=getCateList)

请求方式：GET

参 数：

无


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "1",  // 分类id
            "name": "设计", // 分类名称
            "sort": "1", // 排序参数
            "pid": "0", // 分类父id 为0说明是一级分类
            "is_delete": "0" // 删除状态
        },
        {
            "id": "2",
            "name": "科技",
            "sort": "2",
            "pid": "0",
            "is_delete": "0"
        }
    ]
}
```

---

* ### 发布-顶级分类

接口地址：[http://API\_DOMAIN/index.php?ctl=api_publish&act=index](http://www.zc.local.com/index.php?ctl=api_publish&act=index)

请求方式：GET

参 数：

无


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "11", //顶级分类id
            "name": "百岁公益", //顶级分类标题
            "sort": "11", //顶级分类排序
            "pid": "0", //顶级分类父级id
            "is_delete": "0", //是否被删除
            "thumb": "", //顶级分类图片
            "description": "" //顶级分类简介
        }
    ]
}
```

---

* ### 发布-二级分类

接口地址：[http://API\_DOMAIN/index.php?ctl=api_publish&act=child](http://www.zc.local.com/index.php?ctl=api_publish&act=child&pid=_pid)

请求方式：GET

参 数：

父级分类id（pid/_pid) int


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "12", //子分类id
            "name": "大病救助", //子分类标题
            "sort": "12", //子分类排序
            "pid": "11", //父分类id
            "is_delete": "0", //是否被删除
            "thumb": "", //子分类图片
            "description": "" //子分类id简介
        }
    ]
}
```

---

* ### 发布

接口地址：[http://API\_DOMAIN/index.php?ctl=api_publish&act=publish](http://www.zc.local.com/index.php?ctl=api_publish&act=publish)

请求方式：POST

参 数：

* 父级分类id（pid/_pid) int
* (发布不同，传递的参数不同)
* 大病救助：
* 上级分类id（cate_id/_cate_id) int
* 标题name（name/_name）str
* 简介brief(brief/_brief) str
* 目标金额limit_price(limit_price/_limit_price) str
* 详情description(description/_description) str
* 图片images(images/_images) array
* 房产数量house_num int
* 房产价值house_price int
* 房产状态houst_status int（0-未变卖，1-已变卖）
* 汽车数量car_num int
* 汽车价值car_price int
* 汽车状态car_status int（0-未变卖，1-已变卖）
* 是否该买商业重疾保险is_business int （0-否，1-是）
* 是否按时缴纳医保is_medical int （0-否，1-是）


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": []
}
```

---

* ### 单/多文件上传接口

接口地址：[http://API\_DOMAIN/index.php?ctl=api_deals&act=fileUpload](http://www.zc.local.com/index.php?ctl=api_deals&act=fileUpload)

请求方式：post

参 数：

upload[](文件资源类型)
注意：这里无论单文件还是多文件，上传文件名要写成upload[]


返 回 值：

```

{
"status_code": 200,
"message": "成功",
"data": [ // 这里返回的是根目录下位置
"public/images/api_upload/135938b1f40bacb55a170f7cbbc56017jpg",
"public/images/api_upload/3629423d466ba7cfba52adbf87e6ab50jpg"
]
}
```

---

* ### 创建订单

接口地址：[http://API\_DOMAIN/index.php?ctl=api_order&act=createOrder](http://API\_DOMAIN/index.php?ctl=api_order&act=createOrder)

请求方式：get

参 数：

* 产品id：deal_id int
* 产品单价：money float(10,2)
* 产品优惠：coupon float(10,2)
* 产品数量：count int
* 订单状态：status string unpaid 待支付 paid 待发货(已付款) sent 待收货(已发货) received 已收货
* 支付方式：pay_way string
* 收货地址：address string
* 备注：mark string


返 回 值：

```

{
    "status_code": 200,
    "message": "成功",
    "data": []
}

```

---

* ### 获取订单列表

接口地址：[http://API\_DOMAIN/index.php?ctl=api_order&act=orderList](http://API\_DOMAIN/index.php?ctl=api_order&act=orderList)

请求方式：get

参 数：

* 订单状态：status string unpaid 待支付 paid 待发货(已付款) sent 待收货(已发货) received 已收货
(查询全部不传值)


返 回 值：

```

{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "4", // 订单id 
            "deal_id": "5", // 产品id
            "money": "200.00", // 产品单价
            "coupon": "5.50", // 优惠价格
            "count": "2", // 产品数量
            "status": "unpaid", // 订单状态
            "pay_way": "ailpay", // 支付方式
            "address": "北京", // 收货地址
            "mark": "备注", // 备注
            "deleted_at": "0", // 删除时间
            "created_at": "1498317171", // 创建时间（下单时间）
            "updated_at": "1498317171" // 修改时间
        },
        {
            "id": "3",
            "deal_id": "5",
            "money": "200.00",
            "coupon": "5.50",
            "count": "2",
            "status": "unpaid",
            "pay_way": "ailpay",
            "address": "北京",
            "mark": "备注",
            "deleted_at": "0",
            "created_at": "1498316316",
            "updated_at": "1498316316"
        }
    ]
}


```

* ### 删除订单

接口地址：[http://API\_DOMAIN/index.php?ctl=api_order&act=delOrder](http://API\_DOMAIN/index.php?ctl=api_order&act=delOrder)

请求方式：get

参 数：

* 订单id：id int


返 回 值：

```

{
    "status_code": 200,
    "message": "成功",
    "data": []
}

```

---

* ### 获取已绑定银行卡列表

接口地址：[http://API\_DOMAIN/index.php?ctl=api_user&act=bankLists](http://API\_DOMAIN/index.php?ctl=api_user&act=bankLists)

请求方式：get

参 数：

* 用户ID：user_id int 


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "7", //银行卡id
            "bank_name": "", //银行名称
            "bankcard": "123456789123456", //银行卡号
            "real_name": "王大锤", //银行卡开户名
            "genre": "1" //类别 1-个人 2-对公
        },
        {
            "id": "8",
            "bank_name": "",
            "bankcard": "123456789123456",
            "real_name": "王大锤",
            "genre": "1"
        }
    ]
}


```

---

* ### 添加银行卡页面，获取银行列表

接口地址：[http://API\_DOMAIN/index.php?ctl=api_user&act=bank](http://API\_DOMAIN/index.php?ctl=api_user&act=bank)

请求方式：get

参 数：

* 无


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": [
        {
            "id": "1", //银行ID
            "name": "中国工商银行" //银行名称
        },
        {
            "id": "2",
            "name": "中国农业银行"
        }
    ]
}


```

---

* ### 执行添加银行卡页面

接口地址：[http://API\_DOMAIN/index.php?ctl=api_user&act=bankAdd](http://API\_DOMAIN/index.php?ctl=api_user&act=bankAdd)

请求方式：post

参 数：

* 用户ID user_id
* 业务所属 genre 1-个人；2-对公
* 银行ID bank_id
* 银行名称 bank_name
* 开户名 real_name
* 银行卡号 bankcard


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": []
}


```

---

* ### 删除已绑定的银行卡

接口地址：[http://API\_DOMAIN/index.php?ctl=api_user&act=bankDel](http://API\_DOMAIN/index.php?ctl=api_user&act=bankDel)

请求方式：get

参 数：

* 用户ID user_id
* 银行卡ID id


返 回 值：

```
{
    "status_code": 200,
    "message": "成功",
    "data": []
}


```



