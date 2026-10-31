# SkidSense 发布

SkidSense 的安装包和自动更新源。源代码在私有仓库里，这里只放发布版本。

到 [Releases](https://github.com/LoserLiunian/SkidSense-Release/releases/latest) 下载对应的安装包：

| 系统 | 文件 |
|---|---|
| macOS（Apple 芯片） | `SkidSense-<版本>-mac-arm64.dmg` |
| macOS（Intel） | `SkidSense-<版本>-mac-x64.dmg` |
| Windows（x64） | `SkidSense-<版本>-win-x64.exe` |
| Windows（ARM） | `SkidSense-<版本>-win-arm64.exe` |
| Linux（x64） | `SkidSense-<版本>-linux-x86_64.AppImage` |

安装包要和本机架构一致，装错架构的包会启动失败。

### 手机版

手机版单独发布，版本标签是 `mobile-v<版本>`。到 [Releases](https://github.com/LoserLiunian/SkidSense-Release/releases) 里找标题为「SkidSense 手机版」的那一条：

| 系统 | 文件 |
|---|---|
| Android（大多数手机） | `SkidSense-<版本>-android-arm64.apk` |
| Android（32 位 ARM，较旧的手机） | `SkidSense-<版本>-android-arm.apk` |
| Android（不确定选哪个） | `SkidSense-<版本>-android-universal.apk` |
| iPhone（需要自己签名安装） | `SkidSense-<版本>-ios.ipa` |

Android 版会自己检查更新，读的是这个仓库里的 `mobile.release.json`（打开 Beta 更新后也读 `mobile.beta.json`）。iPhone 版没有应用内更新。

## 更新

- **Windows、Linux AppImage**：应用在后台检查并下载新版本，下载好后提示重启；不重启的话，下次退出时自动安装。
- **macOS**：安装包没有签名，系统不允许它自动替换自己。有新版本时应用会提示，点「下载新版本」打开安装包，把 SkidSense 拖进「应用程序」替换旧版。

在「设置 → 系统设置 → 应用更新」里可以手动检查，也可以打开 Beta 更新，接收预发布版本。

## macOS 首次打开

安装包没有签名，第一次打开时系统可能提示“无法验证开发者”或“已损坏”。在终端里执行一次：

```sh
xattr -dr com.apple.quarantine /Applications/SkidSense.app
```

之后就能正常打开。
