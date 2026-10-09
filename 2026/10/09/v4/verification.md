# Labnote 2026-10-09 存证账本 TSA 补充版 v4

本版补充原 ledger-2026-10-09 中的 11 条指纹，11 条均已取得并验证 FreeTSA 时间戳。原版本、原标签和原附件保持不变。

直接打开 fingerprints.txt，每行包含指纹、TSA 时间（北京时间 UTC+08:00）、服务和序列号。timestamps.json 包含原始 TSA 请求、响应、签名和包含证明，可按 timestamp-verification.md 独立验证。

原记录日期为 2026-10-09。补签实际发生在北京时间 2026-10-10 05:59 左右；本补充清单的独立时间戳为 2026-10-09T22:25:30Z（UTC）。这些时间不追溯到日志创建时间，不证明实验事实真实。

原 manifest SHA-256: 4244edbee7bdbfe666bc904cf17fade3cc85f7feff51ee92f893f18a6a058b50
本版 fingerprints.txt SHA-256: 05d0598feb2278fe5072847377e77bf6e154650b5376880dee4e1a3cc46a3821
本版 manifest.json SHA-256: a32a321c12f0aae9dfad3bbd24210e3b4578732cf8f5bd99abe59f1a949167fd
本版 timestamps.json SHA-256: db7079d218ca44e0de36812df5bec66dc161102a10936adef64a862c45509bfc

公开材料不含日志正文、标题、作者或原始附件；完整原文绑定验证需授权取得私人存证包。验证不包含证书撤销状态检查。

本版仅增加序列号十六进制显示列，两列表示同一个序列号；原始 TSA 材料与 v2 一致，没有重新签发时间戳。清单生成时间沿用 v2，本展示修订于 2026-10-10（北京时间）发布。

## FreeTSA 在线验证入口

[打开 FreeTSA 在线验证](https://www.freetsa.org/index_en.php#online)

进入 **Online Signature → Verify**，分别上传同一份私人存证包中的 `timestamp.tsq` 和 `timestamp.tsr`，再点击 `verify`。出现 `Verification: OK` 表示请求与时间戳响应验证通过。`Serial number` 使用十六进制，可与指纹清单中的十六进制序列号对照。

不要上传整个 ZIP 或日志正文；本账本的 `timestamps.json` 不能直接上传到该页面，应按文中的命令验证。在线验证这两个文件不等于完成原文及附件的整条证据链验证。

## 按十进制序列号下载验证文件

下载 [timestamp-files.zip](timestamp-files.zip) 并解压。按 fingerprints.txt 中的十进制序列号选择同名的一对文件，例如 `152339769.tsq` 和 `152339769.tsr`；包内 `index.tsv` 列出完整指纹与文件名的对应关系。

打开 https://www.freetsa.org/index_en.php#online ，选择 Online Signature → Verify，上传配套文件。原始请求和响应直接从 timestamps.json 提取，没有重新申请时间戳；该在线验证不替代完整原文证据链核验。
