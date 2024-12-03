自动激活+能量下单

请求地址：POST /openapi/tron/energy/order/batchPay

```js
请求的数据：
{
   "apiKey":"用户申请的apiKey",
   "payNums":"能量数量",
   "rentTime":"租赁时长，最小1小时",
   "receiveAddress":"能量接受地址",
   "orderNotes":"订单备注"
}
返回数据：
{
   "code": 0,
   "msg": "success",
   "data": {
       "orderId": "20241128114923171614", //订单编号
       "balance": 8627.675173936600012864, //账户余额：单位trx
       "orderMoney": 1.128322050000000000, //实际扣费金额，单位：trx
       "activationHash": "88081551-d921-4cd8-ae40-37ed5ab0d066", //激活hash
       "hash": [], //能量代理hash
   },
}

curl脚本例子：
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/order/batchPay' \
--header 'Content-Type: application/json' \
--data '{
   "apiKey":"1111",
   "payNums":"33333",
   "rentTime":"1",
   "receiveAddress":"",
   "orderNotes":"1"
}'
```
