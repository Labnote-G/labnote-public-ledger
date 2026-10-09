# 每日指纹与独立时间戳

直接打开 fingerprints.txt，每条指纹后依次显示 TSA 时间（北京时间）、服务和序列号；待签发记录不填写替代时间。
timestamps.json 的 index.records 列出当日正式版本及当日补签完成的版本；同日中间修订也可出现，范围不同于 fingerprints.txt 的每日志当日最后版本。
log_fingerprint 是页面日志整体指纹；timestamp_time 是 UTC 签发时间；timestamp_serial 和 tsa_provider 标识原始响应。非 VERIFIED 表示当时未取得独立时间戳，成功后会出现在签发日的清单，旧清单不改写。
evidence 内的 manifest_base64、signature_base64、request_base64、response_base64 是 Base64 编码的原始材料，proof 是公开的摘要包含证明。没有日志正文、标题、用户信息、文件名、路径或原始附件。

## 验证
从 https://labnote.work/trust/ 独立取得并核实 Labnote 公钥，从 FreeTSA 官方取得并核实根证书。准备 Labnote 验证工具及依赖后运行：
ruby bin/labnote-verify-timestamps --index timestamps.json --trusted-labnote-key labnote-key.pem --trusted-tsa-roots tsa-roots.pem
新版工具同时验证清单签名、清单自身时间戳以及每份 VERIFIED 记录的 Manifest 签名、包含证明和原始 TSA 响应。不能直接把此 JSON 交给私人 ZIP 验证命令。

## 证明边界
清单签名证明平台声明了“日志整体指纹与独立证据”的对应关系；清单自身时间戳证明此清单最晚在其签发时已经存在。
单版本原始时间戳直接绑定的是私有快照的承诺。公开清单不披露快照，因此无法仅凭公开材料重新计算日志整体指纹或核实原始附件；需要授权取得对应私人存证包和原件进一步核验。不能把较晚生成的清单当作较早签发时已有同一公开对应关系的独立证明。
所有验证均未包含证书撤销状态检查，不证明实验事实真实。旧版公开文件与已发布历史标签保持原样。

## FreeTSA 在线验证入口

[打开 FreeTSA 在线验证](https://www.freetsa.org/index_en.php#online)

进入 **Online Signature → Verify**，分别上传同一份私人存证包中的 `timestamp.tsq` 和 `timestamp.tsr`，再点击 `verify`。出现 `Verification: OK` 表示请求与时间戳响应验证通过。`Serial number` 使用十六进制，可与指纹清单中的十六进制序列号对照。

不要上传整个 ZIP 或日志正文；本账本的 `timestamps.json` 不能直接上传到该页面，应按文中的命令验证。在线验证这两个文件不等于完成原文及附件的整条证据链验证。

## 按十进制序列号下载验证文件

下载 [timestamp-files.zip](timestamp-files.zip) 并解压。按 fingerprints.txt 中的十进制序列号选择同名的一对文件，例如 `152339769.tsq` 和 `152339769.tsr`；包内 `index.tsv` 列出完整指纹与文件名的对应关系。

打开 https://www.freetsa.org/index_en.php#online ，选择 Online Signature → Verify，上传配套文件。原始请求和响应直接从 timestamps.json 提取，没有重新申请时间戳；该在线验证不替代完整原文证据链核验。
