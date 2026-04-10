<div style="text-align: right"><a href="../../en/latest/plugins.html">🇺🇸 English</a> | <a href="../../zh-cn/latest/plugins.html">🇨🇳 简体中文</a> | <a href="../../zh-tw/latest/plugins.html">🇭🇰 繁體中文</a> | <a href="../../ja/latest/plugins.html">🇯🇵 日本語</a></div>

# 插件

quardCRT 從 V0.4.0 開始支援外掛。外掛以 Qt 外掛方式實作，並以動態函式庫形式載入。

本頁同時說明兩個面向：

- 一般使用者如何理解與使用外掛功能
- 開發者如何基於 quardCRT 外掛 API 編寫外掛

## 面向使用者

外掛可依自身能力，從多個方向擴充 quardCRT，例如：

- 為主介面加入動作或選單
- 向終端右鍵選單加入項目
- 在應用側邊欄區域提供自訂外掛面板
- 觸發與連線相關的操作，例如開啟 SSH、序列埠、Raw Socket 或 VNC 工作階段

quardCRT 亦提供外掛資訊視窗，用於展示外掛狀態、相容性資訊與初始化錯誤。

### 外掛載入行為

啟動時，quardCRT 會嘗試從自身外掛目錄載入內建外掛。如果你在應用設定中配置了額外的外掛目錄，也會嘗試從該目錄載入外掛。

若某個外掛載入失敗，quardCRT 不會靜默地將其視為成功，而是會在外掛資訊對話框中記錄失敗原因。

常見原因包括：

- 缺少外掛中繼資料
- 外掛 API 版本不受支援
- 初始化失敗
- 缺少 quardCRT 預期的選單或元件入口點

### 啟用與停用外掛

外掛啟用狀態會儲存在應用設定中。對於支援的外掛，可在外掛資訊對話框中啟用或停用。

這在以下場景中很有用：

- 想暫時停用某個外掛而不刪除其檔案
- 測試新外掛時希望可以快速回退
- 想在不同機器上使用不同的外掛組合

## 面向開發者

### API

外掛 API 規範維護在 [plugininterface](https://github.com/QuardCRT-platform/plugininterface) 倉庫中。

開發自訂外掛時，常見流程如下：

- 包含 plugininterface.h 標頭檔
- 定義外掛類別並繼承 PluginInterface
- 實作 PluginInterface 要求的方法
- 針對目標平台建構 `dll`、`so` 或 `dylib` 等原生外掛函式庫
- 將建構好的外掛放到 quardCRT 可以載入的位置

### 模板工程

對於新的外掛開發，建議使用 GitHub 模板工程 [plugin-template](https://github.com/QuardCRT-platform/plugin-template)。

該模板已包含：

- 外掛開發所需的專案結構
- 建構腳本與工程配置
- 基於 GitHub Actions 的 CI 設定

這樣你可以把更多精力放在外掛邏輯本身，而不是從零建立專案骨架。

## 更多

若想了解更多資訊、模板與相關倉庫，請參考 quardCRT 外掛開放平台：

- [https://github.com/QuardCRT-platform](https://github.com/QuardCRT-platform)

外掛系統仍在持續演進中。如果你對外掛 API、擴充點或開發者工具有想法，歡迎在 GitHub 或 Gitee 上提交 issue 或 discussion。
