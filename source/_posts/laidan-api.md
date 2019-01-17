---
title: laidan-api
date: 2018-11-30 15:55:47
tags:
---

header
```
authorization: Bearer 1f7a45f2f307405fa826b15dca114d61
```
# 订单搜索

```
请求路径：
http://localhost:8080/appWeb/api2/order/searchByPage

请求参数：
{"queryDate":"2018-11-01", "pageNum":1, "pageSize":10, "restaurantId":"1264", "partner":"MEI_TUAN", "isBook":true}

返回参数：

{
    "totalRows": 1,
    "pageSize": 10,
    "currPageNum": 1,
    "totalPages": 1,
    "startRow": 0,
    "endRow": 1,
    "pageData": [
        {
            "createDate": 1541067097000,
            "updateDate": 1541067097000,
            "address": "柳营路309弄2号 (501室)",
            "consignee": "miss潘(女士)",
            "partnerCreateDate": "2018-11-01 18:11:18.0",
            "deliverFee": 3,
            "packageFee": 0,
            "deliverTime": "2018-11-01 19:30:00.0",
            "description": "收餐人隐私号 13148114101_7520，手机号 137****2700",
            "detailObject": null,
            "detail": "",
            "invoice": "",
            "isBook": true,
            "isOnlinePaid": true,
            "partnerOrderId": "60572173076323771",
            "phoneList": "13148114101_7520",
            "tpRestaurantId": null,
            "restaurantId": "1264",
            "restaurantName": "鮑佛爺佛跳墙捞饭(西藏北路店)",
            "doorId": null,
            "partnerRestaurantId": "1264",
            "partnerRestaurantName": "鮑佛爺佛跳墙捞饭(西藏北路店)",
            "restaurantNumber": "18",
            "status": "STATUS_CODE_PROCESSED_AND_VALID",
            "totalPrice": 27,
            "originalPrice": 27.88,
            "userId": "miss潘(女士)",
            "username": "miss潘(女士)",
            "deliveryGEO": "121.46412,31.268764",
            "latitude": null,
            "longitude": null,
            "deliveryPoiAddress": null,
            "partner": "MEI_TUAN",
            "printDetail": "^H3 顾客联 \n\n^H3*********No18 美团外卖*********\n^H2         *鲍佛爷（西藏北路店）*\n单号：60572173076323771\n下单时间：2018-11-01 18:11:18\n^H2是预定\n^H2送餐时间：2018-11-01 19:30:00\n ^H2备注：收餐人隐私号 13148114101_7520，手机号 137****2700\n ------------1号口袋------------\n^H2商品名称             数量  单价\n^H2鮑汁紅棗扣花膠/汉\n^H2宫藏娇　　　　　　     *1   42\n\n-------------其它-------------\n@@2配送费　　　　　　         3.0\n\n******************************\n^H3 (已在线支付) 实付金额： 27.0元 \n------------------------------\n^H3用户名称：miss潘(女士)\n^H3订单电话：13148114101_7520\n^H3订单地址：柳营路309弄2号 (\n^H3　　　　　501室)\r\r\r\r\r\r^H4查验过去， 预支未来 扫一扫\n^Q2http://web.yunjuhe.vip/loansearch/list/v1.0/500102",
            "printId": null,
            "printStatus": "PrintSuccess",
            "partnerPrice": 6.12,
            "deliveryType": null,
            "orderType": "WAIMAI",
            "startDate": null,
            "endDate": null,
            "queryDate": null,
            "book": true,
            "timeout": false,
            "createDateText": "2018-11-01 18:11:37",
            "onlinePaid": true,
            "statusName": "订单已处理",
            "printStatusName": "已成功",
            "printDetailInPage": "^H3 顾客联 

^H3*********No18 美团外卖*********
^H2         *鲍佛爷（西藏北路店）*
单号：60572173076323771
下单时间：2018-11-01 18:11:18
^H2是预定
^H2送餐时间：2018-11-01 19:30:00
 ^H2备注：收餐人隐私号 13148114101_7520，手机号 137****2700
 ------------1号口袋------------
^H2商品名称             数量  单价
^H2鮑汁紅棗扣花膠/汉
^H2宫藏娇　　　　　　     *1   42

-------------其它-------------
@@2配送费　　　　　　         3.0

******************************
^H3 (已在线支付) 实付金额： 27.0元 
------------------------------
^H3用户名称：miss潘(女士)
^H3订单电话：13148114101_7520
^H3订单地址：柳营路309弄2号 (
^H3　　　　　501室)\r\r\r\r\r\r^H4查验过去， 预支未来 扫一扫
^Q2http://web.yunjuhe.vip/loansearch/list/v1.0/500102",
            "partnerName": "美团外卖",
            "orderTypeName": "外卖配送",
            "id": "0fcb9402c70941d2968ebf73467bb432"
        }
    ]
}
```


# 注册

```
请求路径：
http://localhost:8080/appWeb/api/register

请求参数：


{
    "password":"123456",
    "phone":"15261771668",
    "userName":"fesfe",
    "validCode":"fesf"
}


返回参数：

```

# 发送短信

```
请求路径：
http://localhost:8080/appWeb/api/sendValidCode

请求参数：


{
    "phone":"15261771668"
}


返回参数：

```

# 未配送搜索

```
请求路径：
http://localhost:8080/appWeb/api2/order/searchNew

请求参数：
{"restaurantId":"1264”}

返回参数：

{
    "count": 4,
    "orders": [
        {
            "createDate": 1542469177000,
            "updateDate": 1542469176000,
            "address": "华科公寓汶水东路670号 206室",
            "consignee": "吉**",
            "partnerCreateDate": "2018-11-17 23:39:40.0",
            "deliverFee": 12,
            "packageFee": 0,
            "deliverTime": "2018-11-17 23:39:40.0",
            "description": "",
            "detailObject": null,
            "detail": "",
            "invoice": "",
            "isBook": false,
            "isOnlinePaid": true,
            "partnerOrderId": "3032320902443085050",
            "phoneList": "17091310151,447",
            "tpRestaurantId": null,
            "restaurantId": "1264",
            "restaurantName": "鮑佛爺佛跳墙捞饭(西藏北路店)",
            "doorId": null,
            "partnerRestaurantId": "167518532",
            "partnerRestaurantName": "鮑佛爺佛跳墙捞饭（西藏北路店）",
            "restaurantNumber": "26",
            "status": "STATUS_CODE_PROCESSED_AND_VALID",
            "totalPrice": 135.3,
            "originalPrice": 124.48,
            "userId": "2986496",
            "username": "2986496",
            "deliveryGEO": "121.47513589,31.28965803",
            "latitude": null,
            "longitude": null,
            "deliveryPoiAddress": null,
            "partner": "ELM",
            "printDetail": "^H3 顾客联 \n\n^H3*********No26 饿了么*********\n^H2         *鮑佛爺炖品·佛跳墙捞饭(西藏北路店)*\n单号：3032320902443085050\n下单时间：2018-11-17 23:39:40\n------------1号口袋------------\n^H2商品名称             数量  单价\n^H2驚喜金湯撈飯/鸡栖\n^H2鲍巢　　　　　　　     *1   42.8\n^H2佛爺招牌金湯佛跳牆\n^H2/金玉滿堂　　　　     *1   45.8\n^H2红豆双皮奶　　　　   *1    12.0\n^H2雪莲炖桃胶　　　　   *1    26.0\n^H2原味双皮奶　　　　   *1    10.0\n^H2餐盒　　　　　　　   *1    6.6\n\n-------------其它-------------\n@@2餐盒费　　　　　　         6.6\n@@2配送费　　　　　　         12.0\n\n******************************\n^H3 (已在线支付) 实付金额： 135.3元 \n------------------------------\n^H3用户名称：2986496\n^H3订单电话：17091310151,447\n^H3订单地址：华科公寓汶水东路670\n^H3　　　　　号 206室\r\r\r\r\r\r",
            "printId": null,
            "printStatus": "PrintSuccess",
            "partnerPrice": 10.82,
            "deliveryType": null,
            "orderType": "WAIMAI",
            "startDate": null,
            "endDate": null,
            "queryDate": null,
            "onlinePaid": true,
            "statusName": "订单已处理",
            "printStatusName": "已成功",
            "printDetailInPage": "^H3 顾客联 

^H3*********No26 饿了么*********
^H2         *鮑佛爺炖品·佛跳墙捞饭(西藏北路店)*
单号：3032320902443085050
下单时间：2018-11-17 23:39:40
------------1号口袋------------
^H2商品名称             数量  单价
^H2驚喜金湯撈飯/鸡栖
^H2鲍巢　　　　　　　     *1   42.8
^H2佛爺招牌金湯佛跳牆
^H2/金玉滿堂　　　　     *1   45.8
^H2红豆双皮奶　　　　   *1    12.0
^H2雪莲炖桃胶　　　　   *1    26.0
^H2原味双皮奶　　　　   *1    10.0
^H2餐盒　　　　　　　   *1    6.6

-------------其它-------------
@@2餐盒费　　　　　　         6.6
@@2配送费　　　　　　         12.0

******************************
^H3 (已在线支付) 实付金额： 135.3元 
------------------------------
^H3用户名称：2986496
^H3订单电话：17091310151,447
^H3订单地址：华科公寓汶水东路670
^H3　　　　　号 206室\r\r\r\r\r\r",
            "partnerName": "饿了么",
            "orderTypeName": "外卖配送",
            "book": false,
            "createDateText": "2018-11-17 23:39:37",
            "timeout": false,
            "id": "311ea8d6e7d742dabc48bcf9f5bbe63e"
        } 
    ],
    “isSuccess": true
}
```

# 商户搜索

```
请求路径：
http://localhost:8080/appWeb/api2/restaruant/search

请求参数：
{}

返回参数：

[
    {
        "createDate": 1542445140000,
        "updateDate": 1542451567000,
        "location": "菜农庄（阳光丽景店）",
        "latitude": null,
        "longitude": null,
        "ownerId": "9",
        "phone": "13683185751",
        "restaurantName": "菜农庄（阳光丽景店）",
        "printMachineId": "303",
        "status": 1,
        "printCount": 0,
        "printCountA": 0,
        "printCountB": 0,
        "printCountC": 0,
        "printCountD": 0,
        "qrcode": null,
        "qrcodeName": null,
        "delay": 7,
        "partners": "美团",
        "id": "1284"
    },
]

```

# 商户保存

```
请求路径：
http://localhost:8080/appWeb/api2/restaruant/save

请求参数：
{
        "printCountA":0,
        "printCountB":1,
        "printCountC":0,
        "printCountD":0,
        "printMachineId":"293",
        "restaurantName":"妙生鲜-正荣店”
}


返回参数

```

# 商户更新

```
请求路径：
http://localhost:8080/appWeb/api2/restaruant/update

请求参数：
{       
         "id":"22222",
        "printCountA":0,
        "printCountB":1,
        "printCountC":0,
        "printCountD":0,
        "printMachineId":"293", 
        "restaurantName":"妙生鲜-正荣店”
}


返回参数

```

# 合作伙伴更新

```
请求路径：
http://localhost:8080/appWeb/api2/partner/updatePartner

请求参数：
{ 
        "id":"22222",
        "managerName":"fefe",
        "managerPhone":"15216771668",
        "doorId":"293",
        "partnerRestaurantName":"妙生鲜-正荣店”
}


返回参数

```

# 财务下载

```
请求路径：
http://localhost:8080/appWeb/api2/finance/download

请求参数：
{
	"startDate":"2018-10-10",
	"endDate":"2018-12-10"
}

```


# 账户保存

```
请求路径：
http://localhost:8080/appWeb/api2/bankAccount/save

请求参数：
{
	"accountName":null,
	"accountNo":null,
	"bankBranch":null,
	"bankName":null,
	"city":null,
	"province":null,
	"restaurantId":null,
}

返回参数

```


# 店铺详情

```
请求路径：
http://localhost:8080/appWeb/api2/restaruant/detail/{resturantId}


请求参数：

返回参数

{
    "data": {
        "BAIDU": {
            "createDate": 1470717392000,
            "updateDate": null,
            "tpRestaurantId": "0",
            "restaurantId": "1003",
            "restaurantName": "所有",
            "managerName":"cheng",
            "managerPhone":"15216771668",
            "doorId": "9999",
            "partnerRestaurantId": "1003",
            "partnerRestaurantName": "美团胡记水果",
            "partnerType": "MEI_TUAN",
            "activities": "使用红包",
            "masterAccount": "NO",
            "accountType": "AUTO",
            "username": "wmhjsg126054",
            "password": "hq830319",
            "sendSms": false,
            "appkey": null,
            "secret": null,
            "accessToken": "0",
            "refreshToken": null,
            "parentId": null,
            "deliveryType": "FEN_NIAO",
            "smsTemplateName": "屌丝奶茶",
            "brandId": "1",
            "brandName": "屌丝奶茶",
            "useMasterAccountSearch": "true",
            "ownerId": "1",
            "status": 1,
            "printMachineId": null,
            "partnerTypeName": "美团外卖",
            "id": "feageggge6067b14b3bae34c83f11sss1"
        },
        "restaurant": {
            "createDate": 1451442711000,
            "updateDate": null,
            "location": "胡记水果",
            "latitude": 11111,
            "longitude": 11111,
            "ownerId": "9999",
            "phone": "13564688428",
            "restaurantName": "胡记水果",
            "printMachineId": "20",
            "status": 1,
            "printCount": 2,
            "printCountA": 0,
            "printCountB": 0,
            "printCountC": 0,
            "printCountD": 0,
            "qrcode": null,
            "qrcodeName": null,
            "delay": 0,
            "partners": null,
            "id": "1003"
        }
    },
    "isSuccess": true,
    "message": "success",
    "success": true
}


```


# 店铺分页查询

```
请求路径：
http://localhost:8080/appWeb/api2/restaruant/searchByPage

请求参数：
{}

返回参数：

{
    "totalRows": 7,
    "pageSize": 10,
    "currPageNum": 1,
    "totalPages": 1,
    "startRow": 0,
    "endRow": 7,
    "pageData": [
        {
            "createDate": 1509159013000,
            "updateDate": 1513239261000,
            "location": "胖先生烤肉拌饭",
            "latitude": null,
            "longitude": null,
            "ownerId": "1",
            "phone": "13811940365",
            "restaurantName": "胖先生烤肉拌饭",
            "printMachineId": "85",
            "status": 2,
            "printCount": 1,
            "printCountA": 0,
            "printCountB": 0,
            "printCountC": 0,
            "printCountD": 0,
            "qrcode": null,
            "qrcodeName": null,
            "delay": 0,
            "partners": "百度",
            "id": "1066"
        },

```

# 发达达

```
请求路径：
http://localhost:8080/appWeb/api2/dada/resend

请求参数：
{“id”:"1111"}

返回参数：
```

# 取消达达

```
请求路径：
http://localhost:8080/appWeb/api2/dada/cancel

请求参数：
{“id”:"1111"}

返回参数：

```

# 保存打印机

```
请求路径：
https://api.laidanl.com/api2/print_machine/save

请求参数：
{
       
        
        "machineCode":"617503914",
        "machineKey":"Lycekzh4",
        "ownerId":"1f7a45f2f307405fa826b15dca114d61",
        "printMachineType":"FEIE"
        
}

打印机类型

YI_LIAN_YUN("易联云"), SAN_LIU_WU("365"), SAN_LIU_WU2("365_2"), FEIE("飞鹅");

返回参数：

```


# 打印机列表

```
请求路径

https://api.laidanl.com/api2/print_machine/search

请求参数
{
       
}

返回参数


```
# 删除打印机

```
https://api.laidanl.com/api2/print_machine/delete

请求参数
{

}

返回参数
```

# 打印

```
https://api.laidanl.com/api2/print_machine/print
请求参数
{

}

返回参数

```
