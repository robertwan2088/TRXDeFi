## Query balance interface
Query user balance and price

## Interface call
### `POST` `/openapi/tron/energy/user/config`
**The following parameters with `*` are required, and those without `*` are optional**

Request Body

| Name                                   | Type   | Description    |
|----------------------------------------|--------|----------------|
| apiKey<span style="color:red">*</span> | String | apiKey applied by the user    |


Response Body
```JSON
{
  "code": 0,
  "msg": "success",
  "data": {
    "userInfo": {
      "balance": 2790.785, //账户余额
      "state": 1, //用户状态
      "username": "" //账户名称
    },
    "payConfig": { //价格配置
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
```

## Call example
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/user/config' \
--header 'Content-Type: application/json' \
--data '{
   "apiKey": "11111"
}'

```

## Postman Example

![user_config.png](img/user_config.png)


