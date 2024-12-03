查询用户余额和价格

请求地址：POST /openapi/tron/energy/user/config
```js
请求参数：
{
   "apiKey": "用户申请的apiKEY"
}
返回数据：
{
   "code": 0,
   "msg": "success",
   "data": {
       "userInfo": {
           "balance": 2790.785, //账户余额
           "state": 1, //用户状态
           "username": "" //账户名称
       },
       "payConfig": { //价格配置
           "energy": {
               "canPay": 1,
               "limit": {
                   "min": 32000,
                   "max": 63028
               },
               "priceConfig": {
                   "1440": 85.0,
               }
           },
           "bandwidth": {
               "canPay": 1,
               "limit": {
                   "min": 32000,
                   "max": 0
               },
               "priceConfig": null
           }
       }
   },
   "totalCount": 0
}


curl脚本例子：
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/user/config' \
--header 'Content-Type: application/json' \
--data '{
   "apiKey": "11111"
}'
```
