查询平台所有类型价格

请求地址：POST /openapi/tron/energy/allPrice

```js
返回数据：
{
   "code": 0,
   "msg": "success",
   "data": {
       "energy": { //能量价格
           "canPay": 1,
           "limit": {
               "min": 65000,//最小租赁能量数量
               "max": 63025 //最大租赁能量数量
           },
           "priceConfig": {
               "0": 60.0, //其他时长费用，单位sun
               "180": 60.0,
               "420": 60.0,
               "120": 60.0,
               "10": 33.85,//10分钟租赁费用，单位sun
               "60": 33.85
           }
       },
       "bandwidth": { //带宽价格
           "canPay": 1,
           "limit": {
               "min": 32000,
               "max": 0
           },
           "priceConfig": null
       }
   },
}

请求curl脚本例子：
curl --silent --location --request POST 'https://app-api.trxdefi.ai/openapi/tron/energy/allPrice' \
--data ''

```
