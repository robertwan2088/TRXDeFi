笔数订单生命周期回调接口，在笔数模式下的账号配置

说明：HTTP POST 你的服务器回调API。请求你接口必须在5秒内响应200状态码，否则将重试3次

```js
请求参数：
{
"orderId":”201411301111”, // 触发的订单ID
"receiveAddress":", // 触发的接收资源地址
"residue":6, // 剩余笔数
"triggerTransactionId":"", // 触发委托的USDT交易HASH
"recharge":1, // 滞留计费标识。1（滞留计费），0（委托计费）
"state":1, // 订单状态。2（删除）1（委托中），0（停止）
"autoType":0, // 智能托管类型：0（笔数），1：（智能）。
"payment":1, // 1（购买笔数） ，0（其他场景）
"maxDelegateNums":10, // 最大委托笔数
"totalDelegateNums":10, // 累计已委托笔数
"detentionChargeTime":6, // 笔数模式下委托滞留天数
"hash":"", // 代理能量hash
"sign":"", // 回调数据的签名信息。方法：md5();签名验证的数据排除sign字段项
"energyNums":"65000", // 智能合约消耗的能量数。滞留或首笔代理该值为空
"orderMoney":"1.96", // 账号代扣每笔扣费，单位trx
}

```
