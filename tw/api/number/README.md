购买笔数开关开启

请求地址：POST /openapi/tron/energy/auto/switch

```js
请求的数据：
{
"apiKey":"用户申请的apiKey", 
"orderId":"笔数套餐的订单号", 
"receiveAddress":"能量接收地址"
}
返回数据：
{
   "code": 0,//0表示成功，其他失败
   "msg": "success"
}





curl脚本例子：
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/switch' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"orderId":"20241130161513184513",
"receiveAddress":"TEmpD6imRret67vnRW4u2fwVKNfpz3DRbw"
}'
```
