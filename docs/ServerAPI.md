# 服务端API
## 接口说明
### 请求说明
 请求的时候需要在Header中带上两个header

| 字段名 | 数据类型 | 说明 |
| ----- | ------- | --- |
|P-Appid|string| Appid，通过AdminApi获取|
|P-Sign|string|签名|

### 签名规则
base64(Appid+":"+time+":"+sign)

sign具体获得

MD5(appid+time+appsecert)

### 返回说明
| 字段名 | 数据类型 | 说明 |
| ----- | ------- | --- |
| `rs`|int | 0=异常 1=正常|
| `msg`|string|错误消息|
|`data`| array| 数据，接口中的返回值都在此中|

## 预下单
### Api地址
/api/unifiedorder

### 请求方式
POST

### 请求参数
| 字段名 | 数据类型 | 默认值 | 说明 |
| ----- | ------- | ----- | --- |
| `order` | string | - | 订单号 |
| `payment` | int | - | 支付金额，单位分 |
| `subject` | string| - | 订单内容|
|`uid` | int | - |用户系统UID|
| `username` | string | - | 用户名|
| `attach` | string | - | 回调时，需要传回的参数|

### 返回值
| 字段名 | 数据类型 | 说明 |
| ----- | ------- | --- |
| `orderId`|string | 预下单订单号|

## 获得订单状态
### Api地址
/getOrder/:order

### 请求方式
GET

### 请求参数
| 字段名 | 数据类型 | 默认值 | 说明 |
| ----- | ------- | ----- | --- |
| `order` | string | - | 订单号| 

### 返回字段
| 字段名 | 数据类型 | 说明|
| ----- | ------- | --- |
|`orderId`|string|联合订单号|
|`order`|string|订单号|
|`payment`| int|金额 单位分|
|`pay`|int|支付方式|
|`status`|int|状态 0=未支付 1=已支付 2=有退款|
|`success_time`|int|支付成功时间戳|

## 支付成功回调


## 跳转到支付页面
通过预下单接口获得订单号之后，将网页跳转到``pay/pay?orderId=:orderId``即可，系统会根据浏览器环境自动判断对应的支付方式，去调用支付

## 发起退款