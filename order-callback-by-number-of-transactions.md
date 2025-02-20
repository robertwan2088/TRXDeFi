## Order callback
Order start callback, order life cycle callback interface, account configuration in order mode

**Description: HTTP POST your server callback API. The request interface must respond with a 200 status code within 5 seconds, otherwise it will be retried 3 times**

## Server request callback interface
### `POST` `Interface URL you provided`
** The following parameters with `*` are required, and those without `*` are optional**

Request Body

| Name                                                | Type    | Description                                                                                                                   |
|-----------------------------------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------|
| orderId<span style="color:red">*</span>             | String  | Triggered order ID                                                                                                            |
| outTradeNo<span style="color:red">*</span>          | String  | External order number[Added on 12/22]                                                                                         |
| receiveAddress<span style="color:red">*</span>      | String  | Triggered receiving resource address                                                                                          |
| residue<span style="color:red">*</span>             | Integer | Remaining number                                                                                                              |
| triggerTransactionId                                | String  | Triggering USDT transaction HASH                                                                                              |
| recharge<span style="color:red">*</span>            | Integer | Deferred billing identifier. 1 (delayed billing), 0 (entrusted billing)                                                       |
| state<span style="color:red">*</span>               | Integer | Order status. 2 (deleted) 1 (entrusted), 0 (stopped)                                                                          |
| autoType<span style="color:red">*</span>            | Integer | Smart hosting type: 0 (number of transactions), 1: (smart).                                                                   |
| payment<span style="color:red">*</span>             | Integer | 1 (number of purchases), 0 (other scenarios)                                                                                  |
| maxDelegateNums<span style="color:red">*</span>     | Integer | Maximum number of delegates                                                                                                   |
| totalDelegateNums<span style="color:red">*</span>   | Integer | Cumulative number of delegates                                                                                                |
| detentionChargeTime<span style="color:red">*</span> | Integer | Number of days for delegation detention in the number of transactions mode                                                    |
| hash                                                | String  | Proxy energy hash                                                                                                             |
| activeHash                                          | String  | If activated, the activated txid [New on 12/22]                                                                               |
| bandwidthHash                                       | String  | If there is bandwidth, the txid of the bandwidth [New on 12/22]                                                               |
| resourceType                                        | Integer | 0: Energy <br/> 1: Bandwidth [New on 12/22]                                                                                   |
| source                                              | Integer | 0: Collection order [to be developed] <br/> 1: Duration energy order <br/> 2: Number of transactions package [Added on 12/22] |
| energyNums                                          | Long    | The amount of energy consumed by the smart contract. The value is 0 for retention or first proxy                              |
| orderMoney                                          | Long    | Account deduction for each deduction, unit sun                                                                                |
| sign                                                | Decimal | Signature information of callback data. Method: md5(); The data for signature verification excludes the sign field            |

Response Body (**HTTP STATUS=200**: indicates successful notification)

```JSON
{
"code": 0,
"msg": "success"
}

```

## Call example
```bash
curl --silent --location 'The callback address you provided' \
--header 'Content-Type: application/json' \
--data '{
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
"orderMoney": 44000000 }'
 ```

