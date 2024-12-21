## Order opening interface
Order opening interface
**Note: If an order is not used for more than 5 days, the order will be automatically stopped and it will continue to proxy energy after restarting**

## Interface call
### `POST` `/openapi/tron/energy/auto/switch`
**The following parameters with `*` are required, and those without `*` are optional**

Request Body

| Name | Type | Description |
|------------------------------------------------|--------|------------|
| apiKey<span style="color:red">*</span> | String | apiKey applied by the user |
| receiveAddress<span style="color:red">*</span> | String | Energy receiving address |

Response Body
```JSON
{
"code": 0,//0 means success, others fail
"msg": "success"
}

```

## Call example
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/switch' \
--header 'Content-Type: application/json' \
--data '{
 "apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
 "receiveAddress":"TEmpD6imRret67vnRW4u2fwVKNfpz3DRbw"
}'
```
## Postman Example 
![img.png](https://raw.githubusercontent.com/robertwan2088/TRXDeFi/refs/heads/main/readme/img/auto_switch.png)


