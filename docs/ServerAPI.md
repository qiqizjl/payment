# 服务端API
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



## 支付成功回调

## 跳转到支付页面

## 发起退款