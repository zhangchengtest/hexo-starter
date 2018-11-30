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



