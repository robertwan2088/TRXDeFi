Automatic activation + energy order

Request address: POST /openapi/tron/energy/order/batchPay

```js
Requested data:
{
"apiKey":"apiKey applied by the user",
"payNums":"energy quantity",
"rentTime":"rental time, minimum 1 hour",
"receiveAddress":"energy receiving address",
"orderNotes":"order notes"
}
Returned data:
{
"code": 0,
"msg": "success",
"data": {
"orderId": "20241128114923171614", //Order number
"balance": 8627.675173936600012864, //Account balance: unit trx
"orderMoney": 1.128322050000000000, //Actual deduction amount, unit: trx
"activationHash": "88081551-d921-4cd8-ae40-37ed5ab0d066", //Activate hash
"hash": [], //Energy proxy hash
},
}

Example of curl script:
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
