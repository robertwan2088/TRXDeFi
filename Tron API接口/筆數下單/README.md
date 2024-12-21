## 筆數下單接口
筆數下單接口，若地址沒有激活，則自動激活地址

## 接口調用
### `POST` `/openapi/tron/energy/auto/add`
**以下參數帶`*`字段爲必填，不帶`*`號爲選填**

Request Body

| Name                                            | Type    | Description      |
|-------------------------------------------------|---------|------------------|
| apiKey<span style="color:red">*</span>          | String  | 用戶申請的apiKey      |
| resType<span style="color:red">*</span>         | String  | 資源類型：默認填冩 "ENERGY" |
| receiveAddress<span style="color:red">*</span>  | String  | 能量接收地址           |
| payment<span style="color:red">*</span>         | Integer | 默認填冩1，用戶賬號扣款     |
| maxDelegateNums<span style="color:red">*</span> | Integer  | 購買能量筆數           |
| orderNotes                                      | String  | 訂單備注             |



Response Body
```JSON
{
  "code": 0, //0表示成功，其他失敗
  "msg": "success",
  "data": {
    "orderId": "20241128114923171614", //訂單編號
    "balance": 800627173, //賬戶餘額：單位sun
    "orderMoney": 1128322, //實際扣費金額，單位：sun
    "activationHash": "88081551-d921-4cd8-ae40-37ed5ab0d066" //激活hash
  }
}


```

## 調用示例
```bash
curl --silent --location ''https://app-api.trxdefi.ai/openapi/tron/energy/auto/add'' \
--header ''Content-Type: application/json'' \
--data ''{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"resType":"ENERGY",
"receiveAddress":"TU47QEb39dyqrdqFr5VSXkgiUHAof9FFAA",
"payment":1,
"maxDelegateNums":2,
"orderNotes":"1221"
}''


```

## Postman 示例

![img.png](img/auto_add.png)
