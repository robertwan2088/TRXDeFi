## 筆數訂單結束接口
筆數訂單結束接口

**説明：訂單結束以後，若還有剩餘代理次數，則自動退款到賬戶餘額**

## 接口調用
### `POST` `/openapi/tron/energy/auto/over`
**以下參數帶`*`字段爲必填，不帶`*`號爲選填**

Request Body

| Name                                   | Type   | Description |
|----------------------------------------|--------|-------------|
| apiKey<span style="color:red">*</span> | String | 用戶申請的apiKey |
| orderId<span style="color:red">*</span> | String | 筆數下單的訂單號    |





Response Body
```JSON
{
  "code": 0,//0表示成功，其他失敗
  "msg": "success"
}

```

## 調用示例
```bash
curl --silent --location ''https://app-api.trxdefi.ai/openapi/tron/energy/auto/over'' \
--header ''Content-Type: application/json'' \
--data ''{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"orderId":"20241125105934188500"
}''


```
