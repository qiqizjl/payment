# 客户端接口
### 请求说明
所有Api都是json返回，请在header中带上json

## 获得支付信息
### Api地址
/pay/getInfo/:payType/:orderId
### 参数
| 字段名 | 数据类型 | 默认值 | 说明 |
| ----- | ------- | ----- | --- |
| `payType` | string | - | 支付方式 alipayapp:支付宝App weixinapp:微信App |
| `orderID` | string | - | 订单号 |
