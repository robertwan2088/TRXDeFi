## Energy order interface
If the address is not activated, the address will be automatically activated and the energy order will be placed

## Interface call
### `POST` `/openapi/tron/energy/order/batchPay`
**The following parameters with `*` are required, and those without `*` are optional**

Request Body

| Name | Type | Description |
|------------------------------------------------|----------|---------------|
| apiKey<span style="color:red">*</span> | String | apiKey applied by the user |
| payNums<span style="color:red">*</span> | Long | Energy quantity |
| rentTime<span style="color:red">*</span> | Integer | Rental time, minimum 1 hour |
| receiveAddress<span style="color:red">*</span> | String | Energy receiving address |
| orderNotes | String | Order notes |

Response Body
```JSON
{
"code": 0,
"msg": "success",
"data": {
"orderId": "20241128114923171614", //Order number
"balance": 8627.675173936600012864, //Account balance: unit trx
"orderMoney": 1.128322050000000000, //Actual deduction amount, unit: trx
"activationHash": "88081551-d921-4cd8-ae40-37ed5ab0d066", //Activation hash
"hash": [], //Energy proxy hash
}
}

```

## Call example
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/order/batchPay' \ 
--header 'Content-Type: application/json' \
 --data '{
 "apiKey":"1111",
 "payNums":"33333",
 "rentTime":"1",
 "receiveAddress":"",
 "orderNotes":"1" }' 
``` 
## Postman Example
 ![img.png](https://raw.githubusercontent.com/robertwan2088/TRXDeFi/refs/heads/main/readme/img/batchPay.png)

