# Labnote Fingerprint Publication 2026-10-10

This directory publishes SHA-256 fingerprints and available version TSA timestamps for Labnote research log versions recorded on 2026-10-10 (Asia/Shanghai).

It does not publish log titles, bodies, authors, project names, attachment names, or raw files.

## Files

- `fingerprints.txt`
- `manifest.json`
- `verification.md`

## Hashes

- `fingerprints.txt`: `d20c9468b82fc77ffb75a68e7300eb7e36a35371d7d0cb1713171a70b6d3f6da`
- `manifest.json`: `cef6ad9a68cc5fdee83c9de51edb7a49d6df718c70f13ad8ab6d047079d23ff7`

## Verification

`fingerprints.txt` 每行格式：SHA-256指纹 | TSA时间（北京时间 UTC+08:00） | TSA服务 | 序列号（十进制） | 序列号（十六进制）。两列表示同一个序列号，0x 开头的十六进制可与 FreeTSA 的 Serial number 对照。
查找指纹时读取每行第一个 `|` 前的字段；旧版单列文件直接读取整行。跳过空行及 `#` 开头的说明。
“待签发”表示本次导出时未取得已验证时间戳，不用日志时间或 GitHub 提交时间替代。后续补签见后续日期的 timestamps.json。

Recalculate SHA-256 for the entire `fingerprints.txt` (including timestamp columns) and compare it with `manifest.json`.
Recalculate SHA-256 for `manifest.json` and compare it with the value above or the Git commit containing this publication.

The displayed times are a readable summary, not standalone cryptographic proof. Verify original TSA responses in timestamps.json using timestamp-verification.md. Times refer to version evidence commitments; they do not prove an exact file creation time or the truth of experimental results. Certificate revocation checks are not included.
