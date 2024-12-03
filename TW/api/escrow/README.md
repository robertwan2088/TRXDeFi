添加笔数托管订单(笔数套餐，账号代扣)

请求地址：POST /openapi/tron/energy/auto/add

```js
请求的数据：
{
"apiKey":"用户申请的apiKey",
"resType":"ENERGY",//默认填写 ENERGY 类型
"receiveAddress":"能量接收地址",
"payment":1,//默认填写1，用户账号扣款
"maxDelegateNums":2, //购买能量笔数
"orderNotes":"1221" //订单备注
}
返回数据：
{
   "code": 0, //0表示成功，其他失败
   "msg": "success",
   "data": {
       "orderId": "20241128114923171614", //订单编号
       "balance": 8627.675173936600012864, //账户余额：单位trx
       "orderMoney": 1.128322050000000000, //实际扣费金额，单位：trx
   }
}



curl脚本例子：
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/add' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"resType":"ENERGY",
"receiveAddress":"TU47QEb39dyqrdqFr5VSXkgiUHAof9FFAA",
"payment":1,
"maxDelegateNums":2,
"orderNotes":"1221"
}'
```
