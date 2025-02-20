## 查詢餘額接口
查詢用戶餘額和價格

## 接口調用
### `POST` `/openapi/tron/energy/user/config`
**以下參數帶`*`字段爲必填，不帶`*`號爲選填**

Request Body

| Name                                   | Type   | Description    |
|----------------------------------------|--------|----------------|
| apiKey<span style="color:red">*</span> | String | 用戶申請的apiKey    |


Response Body
```JSON
{
  "code": 0,
  "msg": "success",
  "data": {
    "userInfo": {
      "balance": 2790.785, //賬戶餘額
      "state": 1, //用戶狀態
      "username": "" //賬戶名稱
    },
    "payConfig": { //價格配置
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

## 調用示例
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/user/config' \
--header 'Content-Type: application/json' \
--data '{"apiKey": "11111"}'

```

## Postman 示例

![user_config.png](https://raw.githubusercontent.com/robertwan2088/TRXDeFi/refs/heads/main/readme/img/user_config.png)

