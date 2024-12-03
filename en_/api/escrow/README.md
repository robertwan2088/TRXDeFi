Add a number of managed orders (number of packages, account deduction)

Request address: POST /openapi/tron/energy/auto/add

```js
Requested data:
{
"apiKey":"apiKey applied by the user",
"resType":"ENERGY",//Default ENERGY type
"receiveAddress":"Energy receiving address",
"payment":1,//Default 1, user account deduction
"maxDelegateNums":2, //Number of energy purchases
"orderNotes":"1221" //Order notes
}
Returned data:
{
"code": 0, //0 means success, others fail
"msg": "success",
"data": {
"orderId": "20241128114923171614", //Order number
"balance": 8627.675173936600012864, //Account balance: unit trx
"orderMoney": 1.128322050000000000, //Actual deduction amount, unit: trx
} } 
curl script example: 
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/add' \ 
--header 'Content-Type: application/json' \ 
--data '{ 
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
 "resType":"ENERGY",
 "receiveAddress":"TU47QEb39dyqrdqFr5VSXkgiUHAof9FFAA", 
"payment":1, 
"maxDelegateNums":2,
 "orderNotes":"1221" }'
```
