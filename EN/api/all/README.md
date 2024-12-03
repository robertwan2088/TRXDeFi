Query all types of prices on the platform

Request address: POST /openapi/tron/energy/allPrice
```js
Return data:
{
   "code": 0,
   "msg": "success",
   "data": {
       "energy": { //Energy prices
           "canPay": 1,
           "limit": {
               "min": 65000,//Minimum rental energy quantity
               "max": 63025 //Maximum rental energy quantity
           },
           "priceConfig": {
               "0": 60.0, //Other duration charges, unit: sun
               "180": 60.0,
               "420": 60.0,
               "120": 60.0,
               "10": 33.85,//10-minute rental fee, unit sun
               "60": 33.85
           }
       },
       "bandwidth": { //Bandwidth Price
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

```
