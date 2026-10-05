# 2026-10-05 指纹与时间戳对照表

每一行把日志整体指纹与对应版本的 TSA 时间戳放在一起。时间统一显示为 **北京时间（UTC+08:00）**。
时间戳表示相应版本的证据承诺最晚在该时间已存在，**不是文件的精确创建时间，也不证明实验结果真实**。

| 日志整体指纹（SHA-256） | TSA 时间（北京时间） | 签发服务 | 时间戳序列号 | 状态 |
| --- | --- | --- | --- | --- |
| `21e335101efcd12fbd52106826e60e4f16f188e3e16abc38830efbcd18ce2444` | 2026-10-05 14:47:34 | https://freetsa.org/tsr | 149218733 | 已验证（不含撤销检查） |
| `3596209ab350eaa6599595e95b7343151702af3f672cd37e7dd8cacaad3cb1af` | 2026-10-05 11:28:04 | https://freetsa.org/tsr | 149132459 | 已验证（不含撤销检查） |
| `3bda6335177116a7ad64316a3ef0213c1e51841a6ca1cd210b45ab469f94f32e` | 2026-10-05 10:27:33 | https://freetsa.org/tsr | 149106179 | 已验证（不含撤销检查） |
| `57905466edf26e4df6aafeefd10c328a957292560c0f65f9f5205ea385d939b3` | 2026-10-05 11:28:05 | https://freetsa.org/tsr | 149132466 | 已验证（不含撤销检查） |
| `7fe33a2a539e932d36db9321ee9498a40ddacadeb6af0a62973d51940c601bee` | 2026-10-05 10:27:32 | https://freetsa.org/tsr | 149106167 | 已验证（不含撤销检查） |
| `f215ef408e195c71b0811d6ddb233a5fe78b9f7a727622e24cba38468dfd95a7` | 2026-10-05 12:32:10 | https://freetsa.org/tsr | 149159265 | 已验证（不含撤销检查） |

## 文件怎么用

- **本表**：直接查指纹对应的时间。内容由 [timestamps.json](timestamps.json) 的 `index.records` 原样映射，时间仅换算时区。
- **[timestamps.json](timestamps.json)**：原始机器可验证材料。每行记录的 `log_fingerprint` 是指纹，`timestamp_time` 是 UTC 时间，`evidence.response_base64` 是该版本 TSA 原始响应的 Base64 编码；顶层 `response_base64` 则属于整份清单，不能当成每条日志的时间。
- **[fingerprints.txt](fingerprints.txt)**：当日每篇日志的最后版本指纹；本表还可能包含中间修订及当日补签的版本，因此条数可能不同。同一指纹有多条记录时逐条保留。
- **[timestamp-verification.md](timestamp-verification.md)**：验证方法和证明边界。表格本身不是签名证据，验证以签名 JSON、TSA 响应及可信证书为准。

公开对应关系由平台签名声明；版本 TSA 直接绑定私有快照承诺。要进一步核对正文及附件，请使用授权下载的日志存证包和原件。
尚未取得时间戳的记录不填写替代时间；以后补签应查看后续日期清单。GitHub 提交时间、清单签发时间均不能替代版本 TSA 时间。

> 本阅读说明在原清单发布后补充，仅换算时区并展示既有数据；不属于原历史标签或 Release 的签名材料，未重新申请时间戳。
