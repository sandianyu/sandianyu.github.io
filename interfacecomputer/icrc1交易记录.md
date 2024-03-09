
- icrc get_transactions
- @decription 获取icrc代币交易记录
- @params start - 获取数据起始位置 number
- @params length - 获取数据长度 number

返回数据格式:
```
{
  first_index: number, // 数据的起始索引
  log_length: number, // 总数据长度
  transactions: Transaction[], // 当前范围内的数据
  archived_transactions: {
    callback: [ canisterId: string, method: string ], // 获取额外数据需要调用的罐子以及方法
    start: number, // 获取额外数据传入的数据起始索引位置,
    length: number, // 获取额外数据传入的数据长度
    }[], // 超出当前范围，存储在交易记录罐里的数据
}

```
例如：当前罐子存储了20条数据，另1800条数据存储在额外的罐子，
当获取数据的起始索引为1798，长度为30，
则返回数据分为当前token罐子里的返回20条，然后额外罐子里有3条
token canister 和 archive canister 的数据都是 时间小的在前面，所以需要倒序读取