结束笔数订单

接口地址：/openapi/tron/energy/auto/over

```js
请求的数据：
{
"apiKey":"用户申请的apiKey", 
"orderId":"笔数套餐的订单号"
}
返回数据：
{
   "code": 0,//0表示成功，其他失败
   "msg": "success"
}

curl脚本例子：
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/over' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"orderId":"20241125105934188500"
}'
```
