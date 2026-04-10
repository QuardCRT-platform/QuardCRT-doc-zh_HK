<div style="text-align: right"><a href="../../en/latest/installation.html">🇺🇸 English</a> | <a href="../../zh-cn/latest/installation.html">🇨🇳 简体中文</a> | <a href="../../zh-tw/latest/installation.html">🇭🇰 繁體中文</a> | <a href="../../ja/latest/installation.html">🇯🇵 日本語</a></div>

# 安裝

quardCRT 提供 Windows、macOS 與 Linux 安裝包。如果你的平台有官方應用商店條目，通常這是最簡單的安裝方式。否則，你可以從 GitHub、Gitee 或 SourceForge 下載發佈包。

## 下載前建議

- 如果你只是想安裝並使用 quardCRT，選擇與你的作業系統和 CPU 架構相符的安裝包即可。
- 如果你打算在 Windows 上建構或載入原生外掛，建議優先選擇 MSVC 安裝包，以便執行階段與常見 MSVC 外掛工具鏈保持一致。
- 如果你使用 Apple Silicon，請選擇 macOS 的 `arm64` 安裝包。
- 在 Linux 上，如果你需要便攜的單檔啟動方式，可選 AppImage；如果你使用 Debian 系發行版並希望交給套件管理器管理，可選 `deb` 包。

## 應用商店

quardCRT 目前可在以下應用商店取得：

- [![Microsoft Store](https://get.microsoft.com/images/zh-tw%20dark.svg)](https://apps.microsoft.com/detail/quardCRT/9p6102k9qb3t?mode=direct)
- [Spark Store](https://www.spark-app.store/store/application/quardcrt)
- Deepin Store

如果你的平台或發行版商店未列在這裡，請使用下面的發佈包安裝。

## 下載

### 所有平台

要下載最新版本，請造訪以下發佈頁：

- [GitHub Releases](https://github.com/QQxiaoming/quardCRT/releases)
- [Gitee Releases](https://gitee.com/QQxiaoming/quardCRT/releases)
- [SourceForge](https://sourceforge.net/projects/quardcrt/files/)

目前發佈資源提供以下格式：

- Windows:
    - `quardCRT_windows_Vxxx_x86_64_setup.exe`
    - `quardCRT_windows_Vxxx_x86_64_msvc_setup.exe`
- macOS:
    - `quardCRT_macos_Vxxx_x86_64.dmg`
    - `quardCRT_macos_Vxxx_arm64.dmg`
- Linux:
    - `quardCRT_Linux_Vxxx_x86_64.AppImage`
    - `quardCRT_Linux_Vxxx_x86_64.deb`
- 原始碼:
    - `quardCRT_Vxxx_source.tar.gz`
    - `quardCRT_Vxxx_source.zip`

### Windows

Windows 下可選擇 `quardCRT_windows_Vxxx_x86_64_setup.exe` 或 `quardCRT_windows_Vxxx_x86_64_msvc_setup.exe`。

- `setup.exe`：MinGW 建構，適合一般使用者，兼容性較佳。
- `msvc_setup.exe`：MSVC 建構，如果你需要與 MSVC 建構的外掛或其他原生元件保持執行階段相容，建議使用此版本。

#### 安裝

執行安裝程式並依照精靈完成安裝：

1. 選擇語言，然後點擊 `確定`。
2. 點擊 `下一步`。
3. 選擇安裝目錄，然後點擊 `下一步`。
4. 選擇是否建立桌面捷徑，然後點擊 `下一步`。
5. 點擊 `安裝`。
6. 點擊 `完成`。

安裝完成後，你可以從開始選單或桌面捷徑啟動 quardCRT。

### macOS

Intel Mac 請下載 `quardCRT_macos_Vxxx_x86_64.dmg`，Apple Silicon Mac 請下載 `quardCRT_macos_Vxxx_arm64.dmg`。

#### 安裝

開啟 DMG 後，依照一般 macOS 應用安裝方式操作：

1. 雙擊 `quardCRT` 圖示。
2. 將 `quardCRT` 圖示拖曳到 `應用程式` 資料夾。

> 注意：目前提供的 macOS 預先建置安裝包尚未經 Apple 官方簽名。首次開啟時，macOS 可能提示應用程式來自未識別的開發者。如果你信任該安裝包，可執行 `xattr -cr /Applications/quardCRT.app` 去除隔離屬性；如果你不信任它，請不要繞過系統警告，而應改為自行從原始碼建構。

### Linux

Linux 下可以在以下兩種格式中選擇：

- `quardCRT_Linux_Vxxx_x86_64.AppImage`：便攜式單一可執行檔
- `quardCRT_Linux_Vxxx_x86_64.deb`：適用於 Debian、Ubuntu、Deepin 等 Debian 系發行版

#### 安裝

- AppImage

AppImage 不需要安裝，賦予可執行權限後即可直接執行：

```bash
chmod +x quardCRT_Linux_Vxxx_x86_64.AppImage
./quardCRT_Linux_Vxxx_x86_64.AppImage
```

- deb

你可以使用圖形化套件管理器安裝 Debian 套件，也可以在命令列安裝。

命令列安裝：

```bash
sudo dpkg -i quardCRT_Linux_Vxxx_x86_64.deb
```

如果系統回報相依性問題，可改用套件管理器處理，例如：

```bash
sudo apt install ./quardCRT_Linux_Vxxx_x86_64.deb
```

## 首次啟動

安裝完成後，常見的第一步是：

1. 開啟 quardCRT。
2. 如果發行包提示選擇語言，請選擇你需要的介面語言。
3. 透過工作階段管理器或快速連線建立一個連線。
4. 如果需要調整主題、字型、傳輸路徑或高級設定，開啟 `選項 > 全域選項`。

接下來可繼續閱讀 [使用指南](./usage.md)。
