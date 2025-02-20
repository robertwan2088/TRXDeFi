## Order query interface
Order query interface

## Interface call
### `POST` `/openapi/tron/energy/orderData`
**The following parameters with `*` are required, and those without `*` are optional**

Request Body

| Name | Type | Description |
|------------------------------------------------| ----------|--------------|
| apiKey<span style="color:red">*</span> | String | apiKey applied by the user|
| orderId<span style="color:red">*</span> | String | TRXDEFI internal order ID|



Response Body
```JSON
{
 "code": 0,
 "msg": "success",
 "data": {
 "canRenewals": 1, // Whether it can be renewed, 0: No, 1: Yes
 "lockTime": "3", // Lease time in minutes
 "orderId": 2023081949511021, // Order ID
 "orderMoney": "90", // Order consumption, unit TRX
 "orderType": "ENERGY", // Resource type, ENERGY: energy, BANDWIDTH: bandwidth
 "payNums": 65000, // Rental quantity
 "receiveAddress": "", // Receive resource address
 "rentTimeLock": 0, // Whether the resource is locked, 0: not locked, 1: locked
 "state": "Agent in progress", // order status
 "time": "2023-09-06 14:36:26", // Order creation time
 "orderNotes": "Remarks information", // Order notes information
 "hash": [
 {
 "hash": "", // Resource agent transaction Hash
 "recoveryHash": "", // Resource recovery transaction Hash
 "info": "Agent successful", // Transaction status information
 "orderId": "0ff5044858de91b3", // Resource agent transaction ID
 "resNums": 65000, //Number of resource agents
 "sendAddress": "", // Send resource address
 "recoveryTime": "2023-09-09 14:36:30" // Resource recovery time
 }
 ]
 }
}


```

## Calling example
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/activation' \
--header 'Content-Type: application/json' \
--data '{
 "apiKey":"1111",
 "orderId":""
}'

```

## Postman Example
