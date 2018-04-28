title: api detail
date: 2017-10-26 10:42:12
tags:
---
title: api detail

## bug
```
第一波

整体：
 所有页面的标题栏的高度缩小一些
 注意日元和人民币的符号是 ￥ ，是两条杠不是一条杠的

1. app的logo使用, 参见压缩包中 app_logo文件夹下的
2. login页面：
	2.1 不要上面的sign in和退出程序按钮
	2.2 页面元素整体上移一些，NihaoPay的logo再大一点，ai格式的文件参见压缩包
	2.3 用户名和密码的输入框，处理下边框以外，其他都去掉
3. Home页面
	3.1 home页面显示的商户名称，不是admin
	3.2 按钮上的字体颜色修改白色

4. New Order菜单下：
	
	4.1 Show QRcode：展示付款二维码后，客户已经付款，但一直停留在二维码页面，不会跳转到支付成功页面，回到history页面时，显示该订单已经支付成功
	4.2 金额根据币种去处理，如果是日元的金额，是不需要乘100的
	4.3 Add Note: 选择add note 后，弹出一个对话框，输入订单描述
	4.4 金额输入的键盘使用自定义的数字键盘(https://github.com/xuejinwei/NumberKeyboard)

5. History：
	5.1 如果记录很多，上拉刷新时会造成app闪退
	5.2 订单列表中，金额的字体大一号，然后加粗显示
	5.3 search 页面的条件为transaction id，是个输入框
	5.4 详情页面的元素之间的间距定义
	5.5 退款页面的文字和字体
    5.6 将时间转换为本地时间

6. Me页面
 	6.1 显示商户名称
 	6.2 整体字体应该缩小一下
 	6.3 sign out  按钮区域的用的是背景色，不是白色
    
    
第二波

1. 退款输入金额也得是自定义键盘
2. 首页下拉刷新
3. 搜索输入id后查询 改变这个id 在刷新还是原来的查询结果

第三波
1. 退款不输入金额崩溃
2. 新订单金额为0依然可以提交
3. 详情和列表金额显示需要是两位小数


```
## 前提：

```
token
正式域名 : https://apptms.nihaopay.com
测试域名 : http://apptms.aurfy.com

txnToken
正式域名 : https://api.nihaopay.com
测试域名 : https://apitest.nihaopay.com


日元测试账号： sherry@aurfy.com  登录密码：abcd.1234   交易密码：abcd1234

美元测试账号
商户号：M086100288
商户后台登录名：414039913123123@qq.com
商户后台登录密码：abcd.1234
交易密码：709Vej8GjH
txnToken：c7978f40e669f86c6409f029181b3f0aef8621a6173b136b9c22c71c956f6f79
token:
1882aa15dd2a06eebb97f8c597c65640e1f7158e095864e16ea057f103a47c1e


```
[原型](https://modao.cc/app/X5dWShjYRVPcXOBzQX6smmrpZbQVqsK)


##  登陆接口

request url （POST）:

```
http://apptms.aurfy.com/out/login

```

request data:
```
{"username":"develop@nihaopay.com", "password":"nihaopay2018", "machineCode": "helloworld"}    

```

response data:
```

{
    "userContext": {
        "merCode": "M086100288",
        "token": "1882aa15dd2a06eebb97f8c597c65640e1f7158e095864e16ea057f103a47c1e",
        "txnToken": "c7978f40e669f86c6409f029181b3f0aef8621a6173b136b9c22c71c956f6f79",
        "userEmail": "414039913123123@qq.com",
        "subMerCode": null,
        "merName": "HelloMan",
        "currency": "USD",
        "userRole": "Admin"
    },
    "isSuccess": true
}

```
error response :

```
{
    "isSuccess": false,
    "msg": "user not exist"
}

```

##  首页前五条交易以及当天交易总金额



request url (POST):

```
http://apptms.aurfy.com/out/transactions/recentTxn 

```

request data:
```
{}  
```

response data:
```
{
    "transactions": [
        {
            "createDate": "2017-10-26 06:54:16",
            "updateDate": "2017-10-26",
            "txnDate": "2017-10-26 14:57:00",
            "version": "1.2",
            "charset": null,
            "language": "English",
            "txnType": "Purchase",
            "merCode": "M001100271",
            "subMerCode": null,
            "merOrderId": "20171026145628415626",
            "merOrderDate": "20171026",
            "merOrderTime": "145659",
            "merOrderAmount": 0.01,
            "bizCode": "POS",
            "txnAmount": 0.01,
            "exchangeRate": 1,
            "txnStatus": "success",
            "merPrivate1": null,
            "merPrivate2": null,
            "merReserved": null,
            "originalTxnId": null,
            "accessURL": null,
            "clientIP": "180.167.25.154",
            "merOrderDescription": null,
            "browserReturnURL": null,
            "serverNotifyURL": null,
            "deliveryAddressId": null,
            "orderTimeZone": "CN",
            "orderTimeOut": "3",
            "signature": "nosignature",
            "branchId": "a2532b43-cd01-46bf-bbdb-57c3bd16dcb2",
            "saleId": "44ae59ba11314245981c36f00381a0f4",
            "agentId": null,
            "pspId": null,
            "cardOrg": "wechatpay",
            "receiveBankTraceNo": null,
            "sendBankOrderId": null,
            "startTxnDate": null,
            "endTxnDate": null,
            "countIp": null,
            "sumAmount": null,
            "txnFinishDate": "2017-10-26 14:57:02",
            "mappedRespCode": null,
            "merCodes": null,
            "maxAmount": null,
            "minAmount": null,
            "goodsAmount": 0,
            "platformAmount": 0,
            "cancellationFlag": null,
            "paymentRefundAmount": null,
            "cutoffStatus": null,
            "bizCategory": null,
            "terminalID": "QR",
            "currencyName": "USD",
            "id": "20171026145659105687"
        },
        {
            "createDate": "2017-10-26 06:52:10",
            "updateDate": "2017-10-26",
            "txnDate": "2017-10-26 14:51:13",
            "version": "1.2",
            "charset": null,
            "language": "English",
            "txnType": "Purchase",
            "merCode": "M001100271",
            "subMerCode": null,
            "merOrderId": "2017102614501065159",
            "merOrderDate": "20171026",
            "merOrderTime": "145112",
            "merOrderAmount": 0.02,
            "bizCode": "POS",
            "txnAmount": 0.02,
            "exchangeRate": 1,
            "txnStatus": "failure",
            "merPrivate1": null,
            "merPrivate2": null,
            "merReserved": null,
            "originalTxnId": null,
            "accessURL": null,
            "clientIP": "180.167.25.154",
            "merOrderDescription": null,
            "browserReturnURL": null,
            "serverNotifyURL": null,
            "deliveryAddressId": null,
            "orderTimeZone": "US",
            "orderTimeOut": "3",
            "signature": "nosignature",
            "branchId": "a2532b43-cd01-46bf-bbdb-57c3bd16dcb2",
            "saleId": "44ae59ba11314245981c36f00381a0f4",
            "agentId": null,
            "pspId": null,
            "cardOrg": "wechatpay",
            "receiveBankTraceNo": null,
            "sendBankOrderId": null,
            "startTxnDate": null,
            "endTxnDate": null,
            "countIp": null,
            "sumAmount": null,
            "txnFinishDate": "2017-10-26 14:51:13",
            "mappedRespCode": null,
            "merCodes": null,
            "maxAmount": null,
            "minAmount": null,
            "goodsAmount": 0,
            "platformAmount": 0,
            "cancellationFlag": null,
            "paymentRefundAmount": null,
            "cutoffStatus": null,
            "bizCategory": null,
            "terminalID": "QR",
            "currencyName": "USD",
            "id": "20171026145112105686"
        },
        {
            "createDate": "2017-10-26 06:42:18",
            "updateDate": "2017-10-26",
            "txnDate": "2017-10-26 14:45:01",
            "version": "1.2",
            "charset": null,
            "language": "English",
            "txnType": "Purchase",
            "merCode": "M001100271",
            "subMerCode": null,
            "merOrderId": "20171026144442785701",
            "merOrderDate": "20171026",
            "merOrderTime": "144501",
            "merOrderAmount": 0.02,
            "bizCode": "Show QRCode",
            "txnAmount": 0.02,
            "exchangeRate": 1,
            "txnStatus": "success",
            "merPrivate1": null,
            "merPrivate2": null,
            "merReserved": null,
            "originalTxnId": null,
            "accessURL": null,
            "clientIP": "127.0.0.1",
            "merOrderDescription": null,
            "browserReturnURL": "http://nihaopay.com",
            "serverNotifyURL": "http://demo.aurfy.cn:8007/ipn",
            "deliveryAddressId": null,
            "orderTimeZone": "CN",
            "orderTimeOut": "30",
            "signature": "nosignature",
            "branchId": "a2532b43-cd01-46bf-bbdb-57c3bd16dcb2",
            "saleId": "44ae59ba11314245981c36f00381a0f4",
            "agentId": null,
            "pspId": null,
            "cardOrg": "wechatpay",
            "receiveBankTraceNo": null,
            "sendBankOrderId": null,
            "startTxnDate": null,
            "endTxnDate": null,
            "countIp": null,
            "sumAmount": null,
            "txnFinishDate": "2017-10-26 14:41:38",
            "mappedRespCode": null,
            "merCodes": null,
            "maxAmount": null,
            "minAmount": null,
            "goodsAmount": 0,
            "platformAmount": 0,
            "cancellationFlag": null,
            "paymentRefundAmount": null,
            "cutoffStatus": null,
            "bizCategory": null,
            "terminalID": "QR",
            "currencyName": "USD",
            "id": "20171026144501105685"
        },
        {
            "createDate": "2017-10-26 06:41:24",
            "updateDate": null,
            "txnDate": "2017-10-26 14:44:08",
            "version": "1.2",
            "charset": null,
            "language": "English",
            "txnType": "Purchase",
            "merCode": "M001100271",
            "subMerCode": null,
            "merOrderId": "20171026144334758583",
            "merOrderDate": "20171026",
            "merOrderTime": "144407",
            "merOrderAmount": 4.5,
            "bizCode": "Show QRCode",
            "txnAmount": 4.5,
            "exchangeRate": 1,
            "txnStatus": "pending",
            "merPrivate1": null,
            "merPrivate2": null,
            "merReserved": null,
            "originalTxnId": null,
            "accessURL": null,
            "clientIP": "127.0.0.1",
            "merOrderDescription": null,
            "browserReturnURL": "http://nihaopay.com",
            "serverNotifyURL": "http://demo.aurfy.cn:8007/ipn",
            "deliveryAddressId": null,
            "orderTimeZone": "CN",
            "orderTimeOut": "30",
            "signature": "nosignature",
            "branchId": "a2532b43-cd01-46bf-bbdb-57c3bd16dcb2",
            "saleId": "44ae59ba11314245981c36f00381a0f4",
            "agentId": null,
            "pspId": null,
            "cardOrg": "alipay",
            "receiveBankTraceNo": null,
            "sendBankOrderId": null,
            "startTxnDate": null,
            "endTxnDate": null,
            "countIp": null,
            "sumAmount": null,
            "txnFinishDate": null,
            "mappedRespCode": null,
            "merCodes": null,
            "maxAmount": null,
            "minAmount": null,
            "goodsAmount": 0,
            "platformAmount": 0,
            "cancellationFlag": null,
            "paymentRefundAmount": null,
            "cutoffStatus": null,
            "bizCategory": null,
            "terminalID": "QR",
            "currencyName": "USD",
            "id": "20171026144407105684"
        }
    ],
    "totalAmount": "0.03",
    "isSuccess": true,
    "currency": "USD"
}

```



## 退款接口

request url （POST）:

```
http://apptms.aurfy.com/out/transactions/refund

```

request data:
```
{"currency":"USD", "txnId":"20171026144407105684", "pwd":"tK7IVs67cO", "refundAmount": 0.01,
"adminEmail":"heh@nihaopay.com"}
```

response data:
```
{
    "message": "refund success",
    "refundDate": "2017-10-27 10:18:28",
    "refundId": "20171027101823000856",
    "isSuccess": true
}

```
error response :

```
{
    "message": "63(The original transaction failed. You cannot refund, cancel, capture, or release an unsuccessful transaction.)",
    "isSuccess": false
}

```


## 交易详细接口

request url （GET）:

```
http://apptms.aurfy.com/out/transactions/detail/{id}

```

request data:
```

```

response data:
```
{
    "transaction": {
        
        "txnDate": "2017-10-26 15:55:22",
        "merOrderId": "20171026155502908974",
        "txnAmount": 0.01,   
        "txnStatus": "success",
        "merOrderDescription": null,
        "cardOrg": "alipay",
        "txnFinishDate": "2017-10-26 15:52:17",
        "currencyName": "USD",
        "paymentRefundAmount": 0.01,
        "id": "20171026155521105690"
    },
    "isSuccess": true
}


备注：
1. txnStatus可选项
success, pending, closed, failure,cancelled


```
error response :

```
{"isSuccess":false,"message":"transaction not found"}

```


## 交易查询

request url （POST）:

```
http://apptms.aurfy.com/out/transactions/search

```

request data:
```
{"pageNum": 1, "pageSize":10, "txnStatus":"PENDING", "id":"20171026144334758583"} 

备注：
1. txnStatus可选项
SUCCESS, PENDING, CLOSED, FAIL 

```

response data:
```

{
    "isSuccess": true,
    "pagination": {
        "totalRows": 1,
        "pageSize": 10,
        "currPageNum": 1,
        "totalPages": 1,
        "startRow": 0,
        "endRow": 1,
        "pageData": [
            {
                "createDate": "2017-10-26 06:41:24",
                "updateDate": null,
                "txnDate": "2017-10-26 14:44:08",
                "version": "1.2",
                "charset": null,
                "language": "English",
                "txnType": "Purchase",
                "merCode": "M001100271",
                "subMerCode": null,
                "merOrderId": "20171026144334758583",
                "merOrderDate": "20171026",
                "merOrderTime": "144407",
                "merOrderAmount": 4.5,
                "bizCode": "Show QRCode",
                "txnAmount": 4.5,
                "exchangeRate": 1,
                "txnStatus": "pending",
                "merPrivate1": null,
                "merPrivate2": null,
                "merReserved": null,
                "originalTxnId": null,
                "accessURL": null,
                "clientIP": "127.0.0.1",
                "merOrderDescription": null,
                "browserReturnURL": "http://nihaopay.com",
                "serverNotifyURL": "http://demo.aurfy.cn:8007/ipn",
                "deliveryAddressId": null,
                "orderTimeZone": "CN",
                "orderTimeOut": "30",
                "signature": "nosignature",
                "branchId": "a2532b43-cd01-46bf-bbdb-57c3bd16dcb2",
                "saleId": "44ae59ba11314245981c36f00381a0f4",
                "agentId": null,
                "pspId": null,
                "cardOrg": "alipay",
                "receiveBankTraceNo": null,
                "sendBankOrderId": null,
                "startTxnDate": null,
                "endTxnDate": null,
                "countIp": null,
                "sumAmount": null,
                "txnFinishDate": null,
                "mappedRespCode": null,
                "merCodes": null,
                "maxAmount": null,
                "minAmount": null,
                "goodsAmount": 0,
                "platformAmount": 0,
                "cancellationFlag": null,
                "paymentRefundAmount": null,
                "cutoffStatus": null,
                "bizCategory": null,
                "terminalID": "QR",
                "currencyName": "USD",
                "id": "20171026144407105684"
            }
        ],
        "totalAmount": null,
        "totalFee": null
    }
}


```
error response :

```
{"isSuccess":false}

```


## 修改密码

request url （POST）:

```
http://apptms.aurfy.com/out/user/modifypwd

```

request data:
```
{"oldpwd": "nihaopay2018", "newpwd":"nihaopay201asds"} 

```

response data:
```
{
    "isSuccess": true
}

```
error response :

```

{
    "message": "The login password is wrong",
    "isSuccess": false
}

```