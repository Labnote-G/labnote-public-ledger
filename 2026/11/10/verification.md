# Labnote Fingerprint Publication 2026-11-10

This directory publishes SHA-256 fingerprints and available version TSA timestamps for Labnote research log versions recorded on 2026-11-10 (Asia/Shanghai).

It does not publish log titles, bodies, authors, project names, attachment names, or raw files.

## Files

- `fingerprints.txt`
- `manifest.json`
- `verification.md`

## Hashes

- `fingerprints.txt`: `72438634c52d4802a065cad60f4543260e6f8fd6812a62de4569485b448574f5`
- `manifest.json`: `d18d0cf9ab135edcebb265b8531b0a127ede268469096e5f2c193a8721550a04`

## Verification

`fingerprints.txt` 每行格式：Labnote序号 | SHA-256指纹 | TSA时间（北京时间 UTC+08:00） | TSA服务 | 序列号（十进制） | 序列号（十六进制）。末两列表示同一个 TSA 序列号，0x 开头的十六进制可与 FreeTSA 的 Serial number 对照。
Labnote 序号在首次发布时分配，同一日志的各版本沿用同一序号。它是日志标识，不是 TSA 序列号。
查找指纹时按 columns 说明读取第二列；历史无 Labnote 序号的文件读取第一列，旧版单列文件直接读取整行。跳过空行及 `#` 开头的说明。
“待签发”表示本次导出时未取得已验证时间戳，不用日志时间或 GitHub 提交时间替代。后续补签见后续日期的 timestamps.json。

Recalculate SHA-256 for the entire `fingerprints.txt` (including timestamp columns) and compare it with `manifest.json`.
Recalculate SHA-256 for `manifest.json` and compare it with the value above or the Git commit containing this publication.

The displayed times are a readable summary, not standalone cryptographic proof. Verify original TSA responses in timestamps.json using timestamp-verification.md. Times refer to version evidence commitments; they do not prove an exact file creation time or the truth of experimental results. Certificate revocation checks are not included.
