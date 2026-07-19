# 安装包说明

本目录只存放可直接交付给用户的安装包。

## 当前包

| 文件 | 架构 | 大小 | SHA-256 |
|---|---:|---:|---|
| `macos/Signal_0.1.3_universal.dmg` | universal | 28940768 bytes | `cbdc69768c150ebb151d565b3c546f96f174e46650d58b8e2385712beeecea23` |
| `macos/Signal_0.1.3_aarch64.dmg` | aarch64 | 17721561 bytes | `0b73d5023b8427e23a63d758f90e50f0c8b2861181aee873dbf82e8ce61816f3` |
| `macos/Signal_0.1.3_x64.dmg` | x86_64 | 18412495 bytes | `c40f4f38b98fd40904282d617a7fc752be56a01a5aeeaa8c985276dd7138d190` |

0.1.2 文件仍保留作历史归档；新安装和回归测试请只使用 0.1.3。

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
