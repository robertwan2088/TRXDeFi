## 笔数订单开启接口
笔数订单开启接口

**说明：如果笔数订单超过5天没有使用，则自动停止订单，需要重启开启后才会继续代理能量**

## 接口调用
### `POST` `/openapi/tron/energy/auto/switch`
**以下参数带`*`字段为必填，不带`*`号为选填**

Request Body

| Name                                           | Type   | Description |
|------------------------------------------------|--------|------------|
| apiKey<span style="color:red">*</span>         | String | 用户申请的apiKey |
| receiveAddress<span style="color:red">*</span> | String | 能量接收地址 |


Response Body
```JSON
{
  "code": 0,//0表示成功，其他失败
  "msg": "success"
}

```

## 调用示例
```bash
curl --silent --location 'https://app-api.trxdefi.ai/openapi/tron/energy/auto/switch' \
--header 'Content-Type: application/json' \
--data '{
"apiKey":"c357ef19-b747-4312-b02a-987c9078cd6d",
"receiveAddress":"TEmpD6imRret67vnRW4u2fwVKNfpz3DRbw"
}'

```

## Postman 示例

![img.png](img/auto_switch.png)
