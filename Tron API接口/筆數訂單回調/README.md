## 筆數訂單回調
筆數訂單開啟回調，筆數訂單生命週期回調接口，在筆數模式下的賬號配置

**説明：HTTP POST 你的服務器回調API。請求你接口必須在5秒內響應200狀態碼，否則將重試3次**

## 服務器請求回調接口
### `POST` `您提供的接口URL`
**以下參數帶`*`字段爲必填，不帶`*`號爲選填**

Request Body

| Name                                                | Type    | Description    |
|-----------------------------------------------------|---------|----------------|
| orderId<span style="color:red">*</span>             | String  | 觸髮的訂單ID    |
| receiveAddress<span style="color:red">*</span>      | String  | 觸髮的接收資源地址    |
| residue<span style="color:red">*</span>             | Integer | 剩餘筆數    |
| triggerTransactionId                                | String  | 觸髮委托的USDT交易HASH    |
| recharge<span style="color:red">*</span>            | Integer | 滯留計費標識。1（滯留計費），0（委托計費）    |
| state<span style="color:red">*</span>               | Integer | 訂單狀態。2（刪除）1（委托中），0（停止）    |
| autoType<span style="color:red">*</span>            | Integer | 智能托管類型：0（筆數），1：（智能）。   |
| payment<span style="color:red">*</span>             | Integer | 1（購買筆數） ，0（其他場景）   |
| maxDelegateNums<span style="color:red">*</span>     | Integer | 最大委托筆數  |
| totalDelegateNums<span style="color:red">*</span>   | Integer |  最大委托筆數  |
| totalDelegateNums<span style="color:red">*</span>   | Integer |  累計已委托筆數 |
| detentionChargeTime<span style="color:red">*</span> | Integer | 筆數模式下委托滯留天數   |
| hash                                                | String  | 代理能量hash   |
| energyNums                                          | Long    | 智能合約消耗的能量數。滯留或首筆代理該值爲0  |
| orderMoney                                          | Decimal | 賬號代扣每筆扣費，單位trx   |
| sign                                                | Decimal | 回調數據的籤名信息。方法：md5();籤名驗証的數據排除sign字段項   |


Response Body（**HTTP STATUS=200**：表示通知成功）
```JSON
{
  "code": 0,
  "msg": "success"
}

```

## 調用示例
```bash
curl --silent --location ''您提供的回調地址'' \
--header ''Content-Type: application/json'' \
--data ''{
"orderId": "201411301111", 
"receiveAddress":"",
"residue":6, 
"triggerTransactionId":"", 
"recharge":1, 
"state":1, 
"autoType":0, 
"payment":1, 
"maxDelegateNums":10, 
"totalDelegateNums":10, 
"detentionChargeTime":6, 
"hash":"", 
"sign":"", 
"energyNums":"65000", 
"orderMoney":"1.96" 
}''

```
