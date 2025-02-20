## 歸集接口【暂不支持】
歸集接口判斷對方有沒有U，自動下單能量；
判斷地址是否激活，自動激活地址；
判斷帶寬（小於381）且餘額（小於0.4TRX），自動補充0.4TRX

## 接口調用
### `POST` `/openapi/tron/energy/collect`
**以下參數帶`*`字段為必填，不帶`*`號為選填**

Request Body

| Name                                           | Type    | Description                                                                     |
|------------------------------------------------|---------|---------------------------------------------------------------------------------|
| apiKey<span style="color:red">*</span>         | String  | 用戶申請的apiKey                                                                     |
| receiveAddress<span style="color:red">*</span> | String  | 能量接收地址                                                                          |
| toAddress                                      | String  | 需要轉帳的地址 某些場景下，您並不是給固定地址轉帳，有可能接受方無U，需要消耗額外的能量 此參數會自動判斷，如果對方無U，會代理額外能量，但是會產生一定的費用 |
| outTradeNo                                     | String  | 回調時將帶上此信息，方便接收方關聯訂單 |



Response Body
```JSON
{
  "code": 0,
  "msg": "success",
  "data": {
    "orderId": "20241128114923171614", // 訂單編號
    "balance": 8627000000, // 帳戶餘額：單位sun
    "orderMoney": 1000000, // 實際扣費金額，單位：sun
    "activationHash": "88081551-d921-4cd8-ae40-37ed5ab0d066", // 激活hash
    "hash": [] // 能量代理hash
  }
}


```

## 調用範例
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/collect' \
--header 'Content-Type: application/json' \
--data '{
   "apiKey":"1111",
   "receiveAddress":""
}'

```

## Postman 範例


