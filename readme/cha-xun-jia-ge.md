# 查詢價格

### 查詢價格接口

查詢平台所有類型價格

### 接口調用

#### `POST` `/openapi/tron/energy/allPrice`

**以下參數帶`*`字段爲必填，不帶`*`號爲選填**

Request Body： **空**

Response Body：

```json
{
  "code": 0,
  "msg": "success",
  "data": {
    "energy": { //能量價格
      "canPay": 1,
      "limit": {
        "min": 65000, //最小租賃能量數量
        "max": 63025
        //最大租賃能量數量
      },
      "priceConfig": {
        "0": 60.0,//其他時長費用，單位sun
        "180": 60.0,
        "420": 60.0,
        "120": 60.0,
        "10": 33.85, //10分鐘租賃費用，單位sun
        "60": 33.85
      }
    },
    "bandwidth": { //帶寬價格
      "canPay": 1,
      "limit": {
        "min": 32000,
        "max": 0
      },
      "priceConfig": null
    }
  }
}
```

### 調用示例

```bash
curl --silent --location --request POST 'https://app-api.trxdefi.ai/openapi/tron/energy/allPrice' \
--data ''
```

### Postman 示例

![energy_all_price.png](https://raw.githubusercontent.com/robertwan2088/TRXDeFi/refs/heads/main/readme/img/energy_all_price.png)
