End the order

Interface address: /openapi/tron/energy/auto/over

```js
Requested data:
{
"apiKey":"apiKey applied by the user",
"orderId":"order number of the package"
}
Returned data:
{
"code": 0,//0 means success, others mean failure
"msg": "success"
}

Example of curl script:
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/over' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"orderId":"20241125105934188500"
}'
```
