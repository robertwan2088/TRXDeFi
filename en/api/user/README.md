Query user balance and price

Request address: POST /openapi/tron/energy/user/config

```js
Request parameters:
{
"apiKey": "apiKEY applied by the user"
}
Return data:
{
"code": 0,
"msg": "success",
"data": {
"userInfo": {
"balance": 2790.785, //Account balance
"state": 1, //User status
"username": "" //Account name
},
"payConfig": { //Price configuration
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

Example of curl script:
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/user/config' \
--header 'Content-Type: application/json' \
--data '{
"apiKey": "11111"
}'
```
