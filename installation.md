<div style="text-align: right"><a href="../../en/latest/installation.html">🇺🇸 English</a> | <a href="../../zh-cn/latest/installation.html">🇨🇳 简体中文</a> | <a href="../../zh-tw/latest/installation.html">🇭🇰 繁體中文</a> | <a href="../../ja/latest/installation.html">🇯🇵 日本語</a></div>

# 安装

QuardCRT 是一個跨平台的終端模擬器，它支援 Windows、MacOS 和 Linux。 你可以根據你的平台下載對應的套件。

## 下載

### 所有平台

如果你想下載 QuardCRT 的最新版本，你可以前往以下連結：

- [GitHub Releases](https://github.com/QQxiaoming/quardCRT/releases)
- [Gitee Releases](https://gitee.com/QQxiaoming/quardCRT/releases)
- [SourceForge](https://sourceforge.net/projects/quardcrt/files/)

你應該根據你的平台下載對應的套件。我們提供以下包：

- Windows: 
    - `quardCRT_windows_Vxxx_x86_64_setup.exe`
    - `quardCRT_windows_Vxxx_x86_64_msvc_setup.exe`
- MacOS: 
    - `quardCRT_macos_Vxxx_x86_64.dmg`
    - `quardCRT_macos_Vxxx_arm64.dmg`
- Linux: 
    - `quardCRT_Linux_Vxxx_x86_64.AppImage`
    - `quardCRT_Linux_Vxxx_x86_64.deb`
- Source code: 
    - `quardCRT_Vxxx_source.tar.gz`
    - `quardCRT_Vxxx_source.zip`

### Windows

如果你使用 Windows，你可以下載 `quardCRT_windows_Vxxx_x86_64_setup.exe` 或 `quardCRT_windows_Vxxx_x86_64_msvc_setup.exe` 套件。 `quardCRT_windows_Vxxx_x86_64_setup.exe` 套件是使用 MinGW 建構的，`quardCRT_windows_Vxxx_x86_64_msvc_setup.exe` 套件是使用 MSVC 建構的。 你可以根據你的需求選擇包。 如果你不在乎自訂插件，你可以選擇 `quardCRT_windows_Vxxx_x86_64_setup.exe` 包，它有更好的相容性。

#### 安裝

你可以透過雙擊套件來安裝 QuardCRT，然後按照提示完成安裝。

1. 選擇語言，然後點選 `確定`。
2. 點選 `下一步`。
3. 選擇安裝目錄，然後點選 `下一步`。
4. 選擇創建桌面快捷方式，然後點選 `下一步`。
5. 點選 `安裝`。
6. 點選 `完成`。

### MacOS

如果你使用 MacOS，你可以下載 `quardCRT_macos_Vxxx_x86_64.dmg` 或 `quardCRT_macos_Vxxx_arm64.dmg` 套件。 `quardCRT_macos_Vxxx_x86_64.dmg` 套件是使用 x86_64 建構的，`quardCRT_macos_Vxxx_arm64.dmg` 套件是使用 arm64 建構的。 如果你使用的是 Apple Silicon Mac，你應該選擇 `quardCRT_macos_Vxxx_arm64.dmg` 套件。

#### 安裝

你可以透過雙擊套件來安裝 QuardCRT，然後按照提示完成安裝。

1. 雙擊 `quardCRT` 圖示。
2. 將 `quardCRT` 圖示拖曳到 `應用程式` 資料夾。

> 注意：因為我們目前發布的預先建置二進位套件沒有經過 Apple 官方簽名，所以當你第一次打開程式時，你可能會收到一個警告訊息，提示程式來自未知開發者。 如果你信任我們的程序，你可能需要打開終端機並執行 `xattr -cr /Applications/quardCRT.app` 來移除隔離屬性。 但如果你不信任我們的程序，你不應該運行它。 你可以選擇自己編譯程式。

### Linux

如果你使用 Linux，你可以下載 `quardCRT_Linux_Vxxx_x86_64.AppImage` 或 `quardCRT_Linux_Vxxx_x86_64.deb` 套件。 `quardCRT_Linux_Vxxx_x86_64.AppImage` 套件是一個 AppImage 套件，`quardCRT_Linux_Vxxx_x86_64.deb` 套件是一個 deb 套件。 你可以根據你的需求選擇包。

#### 安裝

AppImage 套件是一個便攜式應用程序，你可以直接運行它而不需要安裝。 你可以運行以下命令使其可執行：

```bash
chmod +x quardCRT_Linux_Vxxx_x86_64.AppImage
```

- deb

你可以透過雙擊包來安裝 deb 包，然後按照提示完成安裝。

1. 雙擊包。
2. 點選 `安裝`。
3. 輸入密碼，然後點選 `驗證`。
4. 點選 `關閉`。

或者你可以透過執行以下命令來安裝 deb 套件：

```bash
sudo dpkg -i quardCRT_Linux_Vxxx_x86_64.deb
```

## 其他應用程式商店

我們也在其他應用程式商店提供 QuardCRT，你可以從應用程式商店下載。 通常安裝步驟更加方便。 現在我們提供以下應用程式商店：

- 深度商店

我們將在未來添加更多的應用程式商店。
