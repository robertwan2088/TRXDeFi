## Address Activation
Automatically activate the address if it is not active

## Interface call
### `POST` `/openapi/tron/energy/activation`
**The following parameters with `*` are required, and those without `*` are optional**

Request Body

| Name | Type | Description |
|------------------------------------------------| ----------|--------------|
| apiKey<span style="color:red">*</span> | String | apiKey applied by the user |
| receiveAddress<span style="color:red">*</span> | String | Energy receiving address|



Response Body
```JSON
{
 "code": 0,
 "msg": "success",
 "data": {
 "balance": 8627000000, //Account balance: unit sun
 "orderMoney": 1000000, //Actual deduction amount, unit: sun
 "txID": "88081551-d921-4cd8-ae40-37ed5ab0d066", //Activate hash
 }
}


```

## Calling example
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/activation' \
--header 'Content-Type: application/json' \
--data '{
 "apiKey":"1111",
 "receiveAddress":""
}'

```

## Postman Example
