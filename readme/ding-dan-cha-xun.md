## 訂單查詢接口
訂單查詢接口

## 接口調用
### `POST` `/openapi/tron/energy/orderData`
**以下參數帶`*`字段為必填，不帶`*`號為選填**

Request Body

| Name                                           | Type    | Description  |
|------------------------------------------------|---------|--------------|
| apiKey<span style="color:red">*</span>         | String  | 用戶申請的apiKey|
| orderId<span style="color:red">*</span> | String  | TRXDEFI內部訂單ID|



Response Body
```JSON
{
  "code": 0,
  "msg": "success",
  "data": {
    "canRenewals": 1, // 是否可以續費，0：不可以，1：可以
    "lockTime": "3", // 租用時間分鐘
    "orderId": 2023081949511021, // 訂單ID
    "orderMoney": "90", // 訂單消費，單位TRX
    "orderType": "ENERGY", // 資源類型，ENERGY：能量，BANDWIDTH：帶寬
    "payNums": 65000, // 租用數量
    "receiveAddress": "", // 接收資源地址
    "rentTimeLock": 0, // 資源是否鎖定，0：不鎖定，1：鎖定
    "state": "代理中", // 訂單狀態
    "time": "2023-09-06 14:36:26", // 訂單創建時間
    "orderNotes": "備註信息", // 訂單備註信息
    "hash": [
      {
        "hash": "", // 資源代理交易Hash
        "recoveryHash": "", // 資源回收交易Hash
        "info": "代理成功", // 交易狀態信息
        "orderId": "0ff5044858de91b3", // 資源代理交易ID
        "resNums": 65000, // 資源代理數量
        "sendAddress": "", // 發送資源地址
        "recoveryTime": "2023-09-09 14:36:30" // 資源回收時間
      }
    ]
  }
}


```

## 調用範例
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/activation' \
--header 'Content-Type: application/json' \
--data '{
   "apiKey":"1111",
   "orderId":""
}'

```

## Postman 範例


