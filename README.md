# Signal static distribution

这个仓库用于静态分发 Signal / Signal Brain 安装包和用户文档，不包含应用源码，也不保存 Rust/Node 构建缓存。

> Signal 是本地 AI 投研认知库桌面应用。它帮助把投喂、自动挖掘和行情/财报/热点线索沉淀为可追溯的认知卡片，再用于分析、图谱、复核、因子验证和决策辅助。应用不连接券商接口，不自动下单，不构成投资建议。

## 下载

当前已收录 macOS 安装包：

| 平台 | 文件 | 建议 |
|---|---|---|
| macOS Intel + Apple Silicon | [Signal_0.1.2_universal.dmg](packages/macos/Signal_0.1.2_universal.dmg) | 不确定芯片架构时优先用这个 |
| macOS Apple Silicon | [Signal_0.1.2_aarch64.dmg](packages/macos/Signal_0.1.2_aarch64.dmg) | M1/M2/M3/M4 Mac |
| macOS Intel | [Signal_0.1.2_x64.dmg](packages/macos/Signal_0.1.2_x64.dmg) | Intel Mac |

校验文件见 [CHECKSUMS.txt](CHECKSUMS.txt)，产物清单见 [packages/manifest.json](packages/manifest.json)。

## 文档

- [快速开始](docs/getting-started.md)
- [模块使用说明](docs/modules.md)
- [安装包说明](packages/README.md)

## 仓库约定

- `packages/`：安装包和静态分发产物。
- `docs/`：面向最终用户的使用文档。
- `CHECKSUMS.txt`：当前安装包的 SHA-256 校验和。
- `packages/manifest.json`：安装包的版本、架构、大小、来源路径和校验信息。

新增安装包时，只提交可直接分发的安装器或压缩包，不提交 `target/deps`、`debug`、`incremental`、`node_modules` 等构建缓存。
