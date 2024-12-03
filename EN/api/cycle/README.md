Order life cycle callback interface, account configuration in order mode

Description: HTTP POST your server callback API. The request to your interface must respond with a 200 status code within 5 seconds, otherwise it will be retried 3 times

```js
Request parameters:
{
"orderId":”201411301111”, // Triggered order ID
"receiveAddress":", // Triggered receiving resource address
"residue":6, // Remaining number
"triggerTransactionId":"", // Triggering USDT transaction HASH
"recharge":1, // Detention charge identification. 1 (detention charge), 0 (delegation charge)
"state":1, // Order status. 2 (delete) 1 (delegated), 0 (stopped)
"autoType":0, // Smart custody type: 0 (number of transactions), 1: (smart).
"payment":1, // 1 (number of purchases), 0 (other scenarios)
"maxDelegateNums":10, // Maximum number of delegates
"totalDelegateNums":10, // Cumulative number of delegates
"detentionChargeTime":6, // Number of days for the order to be retained in the transaction mode
"hash":"", // Proxy energy hash
"sign":"", // Signature information of the callback data. Method: md5(); The data for signature verification excludes the sign field item
"energyNums":"65000", // The amount of energy consumed by the smart contract. The value is empty for retention or first transaction
"orderMoney":"1.96", // Account deduction for each transaction, unit trx
}
```
