## 地址激活接口
如果地址未激活，則自動激活地址

## 接口調用
### `POST` `/openapi/tron/energy/activation`
**以下參數帶`*`字段為必填，不帶`*`號為選填**

Request Body

| Name                                           | Type    | Description  |
|------------------------------------------------|---------|--------------|
| apiKey<span style="color:red">*</span>         | String  | 用戶申請的apiKey  |
| receiveAddress<span style="color:red">*</span> | String  | 能量接受地址|



Response Body
```JSON
{
  "code": 0,
  "msg": "success",
  "data": {
    "balance": 8627000000, //帳戶餘額：單位sun
    "orderMoney": 1000000, //實際扣費金額，單位：sun
    "txID": "88081551-d921-4cd8-ae40-37ed5ab0d066", //激活hash
  }
}


```

## 調用範例
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/activation' \
--header 'Content-Type: application/json' \
--data '{
   "apiKey":"1111",
   "receiveAddress":""
}'

```

## Postman 範例


