## Query price interface
Query all types of prices on the platform

## Interface call
### `POST` `/openapi/tron/energy/allPrice`
**The following parameters with `*` are required, and those without `*` are optional**

Request Body:
**Empty**

Response Body:
```JSON
{
"code": 0,
"msg": "success",
"data": {
"energy": { //Energy price
"canPay": 1,
"limit": {
"min": 65000, //Minimum rental energy quantity
"max": 63025
//Maximum rental energy quantity
},
"priceConfig": {
"0": 60.0,//Other duration fees, unit sun
"180": 60.0,
"420": 60.0,
"120": 60.0,
"10": 33.85, //10 minutes rental fee, unit sun
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
}
}
```

## Call example
```bash
curl --silent --location --request POST 'https://app-api.trxdefi.ai/openapi/tron/energy/allPrice' \
--data ''
```

## Postman example

![energy_all_price.png](https://raw.githubusercontent.com/robertwan2088/TRXDeFi/refs/heads/main/readme/img/energy_all_price.png)

