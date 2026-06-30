# 安装包说明

本目录只存放可直接交付给用户的安装包。

## 当前包

| 文件 | 架构 | 大小 | SHA-256 |
|---|---:|---:|---|
| `macos/Signal_0.1.2_universal.dmg` | universal | 24114873 bytes | `e2c7136dfb45ee61be8f5c8cb7bae93d5c2738223977a27a2c89d746f71e53c1` |
| `macos/Signal_0.1.2_aarch64.dmg` | aarch64 | 14871528 bytes | `985ef7340d25c77959de98a500255ff5a4df231514a7a0352fdaaeeed03d6bdb` |
| `macos/Signal_0.1.2_x64.dmg` | x86_64 | 15456353 bytes | `57f00ca95b4fdf059488c8a229249e0169461f9d71712c38a3f4a75d280bcf65` |

## macOS 安装

1. 下载对应 `.dmg`。
2. 双击打开，把 `Signal.app` 或 `Signal Brain.app` 拖到 `Applications`。
3. 从“应用程序”打开。
4. 如果提示来自未验证开发者，在 Finder 中右键应用，选择“打开”。
5. 如果下载后提示“已损坏”，执行：

```shell
xattr -cr "/Applications/Signal.app"
# 或
xattr -cr "/Applications/Signal Brain.app"
```

## 更新包

源码仓库的打包脚本会把 macOS 产物放在这些位置：

```text
target/release/bundle/dmg/
target/universal-apple-darwin/release/bundle/dmg/
target/x86_64-apple-darwin/release/bundle/dmg/
target/aarch64-apple-darwin/release/bundle/dmg/
```

更新本仓库时，只复制 `.dmg`、`.msi`、`.exe`、`.deb`、`.AppImage` 等最终安装包，并同步更新 `CHECKSUMS.txt` 和 `packages/manifest.json`。
