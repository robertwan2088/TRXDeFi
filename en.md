一.Interface description
Interface address: https://app-api.trxdefi.ai.
Preconditions for accessing the interface:
1. Register an account: https://h5.trxdefi.ai/
2. Apply for appkey: Apply at https://h5.trxdefi.ai/ User Center
3. To call the interface, you need to provide the public IP address of the calling server, and you can access it after authorization.

二. Interface
1. Query all types of prices on the platform
Request address: POST /openapi/tron/energy/allPrice
Return data:
{
"code": 0,
"msg": "success",
"data": {
"energy": { //Energy price
"canPay": 1,
"limit": {
"min": 65000,//Minimum rental energy quantity
"max": 63025 //Maximum rental energy quantity
},
"priceConfig": {
"0": 60.0, //Other duration fees, unit sun
"180": 60.0,
"420": 60.0,
"120": 60.0,
"10": 33.85,//10 minutes rental fee, unit sun
"60": 33.85
}
},
"bandwidth": { //Bandwidth price
"canPay": 1,
"limit": {
"min": 32000,
"max": 0
},
"priceConfig": null
}
},
}

Request curl script example:
curl --silent --location --request POST 'https://app-api.trxdefi.ai/openapi/tron/energy/allPrice' \
--data ''

2. Query user balance and price
Request address: POST /openapi/tron/energy/user/config
Request parameters:
{
"apiKey": "apiKEY applied by the user"
}
Return data:
{
"code": 0,
"msg": "success",
"data": {
"userInfo": {
"balance": 2790.785, //Account balance
"state": 1, //User status
"username": "" //Account name
},
"payConfig": { //Price configuration
"energy": {
"canPay": 1,
"limit": {
"min": 32000,
"max": 63028
},
"priceConfig": {
"1440": 85.0,
}
},
"bandwidth": {
"canPay": 1,
"limit": {
"min": 32000,
"max": 0
},
"priceConfig": null
}
}
},
"totalCount": 0
}

Example of curl script:
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/user/config' \
--header 'Content-Type: application/json' \
--data '{
"apiKey": "11111"
}'

3. Automatic activation + energy order
Request address: POST /openapi/tron/energy/order/batchPay
Request data:
{
"apiKey":"apiKey applied by the user",
"payNums":"energy quantity",
"rentTime":"rental time, minimum 1 hour",
"receiveAddress":"energy receiving address",
"orderNotes":"order notes"
}
Return data:
{
"code": 0,
"msg": "success",
"data": {
"orderId": "20241128114923171614", //Order number
"balance": 8627.675173936600012864, //Account balance: unit trx
"orderMoney": 1.128322050000000000, //Actual deduction amount, unit: trx
"activationHash": "88081551-d921-4cd8-ae40-37ed5ab0d066", //Activation hash
"hash": [], //Energy proxy hash
},
}

Example of curl script:

curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/order/batchPay' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"1111",
"payNums":"33333",
"rentTime":"1",
"receiveAddress":"",
"orderNotes":"1"
}'

4. Add a number of managed orders (number of packages, account deduction)
Request address: POST /openapi/tron/energy/auto/add
Request data:
{
"apiKey":"apiKey applied by the user",
"resType":"ENERGY",//Default ENERGY type
"receiveAddress":"Energy receiving address",
"payment":1,//Default 1, user account deduction
"maxDelegateNums":2, //Number of energy purchased
"orderNotes":"1221" //Order notes
}
Return data:
{
"code": 0, //0 means success, others fail
"msg": "success",
"data": {
"orderId": "20241128114923171614", //Order number
"balance": 8627.675173936600012864, //Account balance: unit trx
"orderMoney": 1.128322050000000000, //Actual deduction amount, unit: trx
}
}

Example of curl script:
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/add' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"resType":"ENERGY",
"receiveAddress":"TU47QEb39dyqrdqFr5VSXkgiUHAof9FFAA",
"payment":1,
"maxDelegateNums":2,
"orderNotes":"1221"
}'

5. Turn on the purchase quantity switch
Request address: POST /openapi/tron/energy/auto/switch
Request data:
{
"apiKey":"apiKey applied by the user",
"orderId":"order number of the quantity package",
"receiveAddress":"energy receiving address"
}
Return data:
{
"code": 0,//0 means success, others fail
"msg": "success"
}
Curl script example:
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/switch' \
--header 'Content-Type: application/json' \
--data '{ "apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d", "orderId":"20241130161513184513", "receiveAddress":"TEmpD6imRret67vnRW4u2fwVKNfpz3DRbw" }'

6. End the order
Interface address: /openapi/tron/energy/auto/over
Requested data:
{
"apiKey":"apiKey applied by the user",
"orderId":"order number of the order package"
}
Returned data:
{
"code": 0,//0 means success, others fail
"msg": "success"
}
Curl script example:
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/over' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"orderId":"20241125105934188500"
}'

7. Order life cycle callback interface, account configuration in order mode
Description: HTTP POST your server callback API. The request interface must respond with a 200 status code within 5 seconds, otherwise it will be retried 3 times

Request parameters:
{
"orderId":”201411301111”, // Triggered order ID
"receiveAddress":", // Triggered receiving resource address
"residue":6, // Remaining number
"triggerTransactionId":"", // Triggering entrusted USDT transaction HASH
"recharge":1, // Deferred billing identifier. 1 (deferred billing), 0 (entrusted billing)
"state":1, // Order status. 2 (deleted) 1 (entrusted), 0 (stopped)
"autoType":0, // Smart custody type: 0 (number of transactions), 1: (smart).
"payment":1, // 1 (purchase number), 0 (other scenarios)
"maxDelegateNums":10, // Maximum number of delegates
"totalDelegateNums":10, // Cumulative number of entrusted transactions
"detentionChargeTime":6, // Delegation retention days in transaction mode
"hash":"", // Proxy energy hash
"sign":"", // Signature information of callback data. Method: md5(); data for signature verification excludes sign field items
"energyNums":"65000", // Energy consumed by smart contract. This value is empty for retention or first agent
"orderMoney":"1.96", // Account deduction for each deduction, unit trx
}
