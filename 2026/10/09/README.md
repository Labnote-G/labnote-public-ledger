# 2026-10-09 存证账本

## 最新版本：v4（已补充 TSA 时间戳）

**[查看新版指纹、TSA 时间和序列号](v4/fingerprints.txt)** · [查看 v4 全部验证文件](v4/) · [下载新版发布附件](https://github.com/Labnote-G/labnote-public-ledger/releases/tag/tsa-supplement-2026-10-09-v4)

v4 包含本日原有 11 条指纹，11 条 TSA 均已验证。补签实际时间为北京时间 2026-10-10 05:59 左右，不是日志创建时间。

本目录根部文件是首次发布的原版快照，保留原样；新版文件集中在 `v4` 子目录。原版与补充版的 Git 标签、发布附件均保持不变。

## FreeTSA 在线验证入口

[打开 FreeTSA 在线验证](https://www.freetsa.org/index_en.php#online)

进入 **Online Signature → Verify**，分别上传同一份私人存证包中的 `timestamp.tsq` 和 `timestamp.tsr`，再点击 `verify`。出现 `Verification: OK` 表示请求与时间戳响应验证通过。`Serial number` 使用十六进制，可与指纹清单中的十六进制序列号对照。

不要上传整个 ZIP 或日志正文；本账本的 `timestamps.json` 不能直接上传到该页面，应按文中的命令验证。在线验证这两个文件不等于完成原文及附件的整条证据链验证。

[下载按十进制序列号命名的 TSA 文件包](v4/timestamp-files.zip)
