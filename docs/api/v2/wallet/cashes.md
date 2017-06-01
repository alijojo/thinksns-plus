# 提现申请

```
POST /wallet/cashes
```

### Input

| 名称 | 类型 | 描述 |
|----|:----:|:----:|
| value | int | 用户需要提现的余额数量 |
| type | string | 用户提现账户方式 |
| account | string | 用户提现账户 |

```json5
{
    "value": 100,
    "type": "alipay"
    "account": "xxx@alipay.com"
}
```

> value 的值是用户输入的余额值按照「转换比例」转换后再转化为「分」单位

##### Headers

```
Status: 201 Created
```

##### Body

```json5
{
  "value": [
    "请输入提现金额", // 用户没用输入
    "发送的数据错误", // 发送错误的数据给服务器（非正整数）
    "输入的提现金额不合法", // 发送给服务器小于 1
    "提现金额超出账户余额", // 用户提现金额超出余额
  ],
  "type": [
    "请选择提现方式", // 没有发送提现方式
    "你选择的提现方式不支持" // 提现的方式后台设置不允许提现
  ],
  "account": [
    "请输入你的提现账户" // 没有输入账户
  ],
  "message": [
    "申请提现成功", // 成功
    "申请失败" // 失败
  ]
}
```