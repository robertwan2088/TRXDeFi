## 查詢價格接口
查詢平台所有類型價格

## 介面調用
### `POST` `/openapi/tron/energy/allPrice`
**以下參數帶`*`欄位為必填，不含`*`號為選填**

Request Body：
**空**

Response Body：
```JSON
{
 "code": 0,
 "msg": "success",
 "data": {
 "energy": { //能量價格
 "canPay": 1,
 "limit": {
 "min": 65000, //最小租賃能量數量
 "max": 63025
 //最大租賃能量數量
 },
 "priceConfig": {
 "0": 60.0,//其他時長費用，單位sun
 "180": 60.0,
 "420": 60.0,
 "120": 60.0,
 "10": 33.85, //10分鐘租賃費用，單位sun
 "60": 33.85
 }
 },
 "bandwidth": { //頻寬價格
 "canPay": 1,
 "limit": {
 "min": 32000,
 "max": 0
 },
 "priceConfig": null
 }
 }
}
```

## 呼叫範例
『`bash
curl --silent --location --request POST 'https://app-api.trxdefi.ai/openapi/tron/energy/allPrice' \
--data ''
```

## Postman 範例

请求curl脚本例子：
curl --silent --location --request POST 'https://app-api.trxdefi.ai/openapi/tron/energy/allPrice' \
--data ''

```
