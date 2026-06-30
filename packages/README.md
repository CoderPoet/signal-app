# 安装包说明

本目录只存放可直接交付给用户的安装包。

## 当前包

| 文件 | 架构 | 大小 | SHA-256 |
|---|---:|---:|---|
| `macos/Signal_0.1.2_universal.dmg` | universal | 22639413 bytes | `b9f1dfba67ff854d5f2a9eb754a658a4527535c18f20f3945b01c2f21f5b9d9c` |
| `macos/Signal_0.1.2_aarch64.dmg` | aarch64 | 13408837 bytes | `401d004e2ff1b77c1ac97fc265fffe3e7151580ab72aa7e6fc50d2d6eaa69188` |
| `macos/Signal_0.1.2_x64.dmg` | x86_64 | 13502219 bytes | `c83449e22c605ff592055b7277fbe5a62d3eef367ffc48052205ed1524a1a77f` |

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
