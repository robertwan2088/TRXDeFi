Purchase quantity switch is turned on

Request address: POST /openapi/tron/energy/auto/switch

```js
Requested data:
{
"apiKey":"apiKey applied by the user",
"orderId":"order number of the package",
"receiveAddress":"energy receiving address"
}
Returned data:
{
"code": 0,//0 means success, others fail
"msg": "success"
}

Example of curl script:
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/switch' \
--header 'Content-Type: application/json' \
--data '{ "apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d", "orderId":"20241130161513184513", "receiveAddress":"TEmpD6imRret67vnRW4u2fwVKNfpz3DRbw" }'
```
