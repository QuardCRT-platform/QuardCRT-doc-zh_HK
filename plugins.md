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

實際上，一個有用的外掛通常會提供以下一項或多項能力：

- 主選單動作或選單
- 側邊欄面板
- 終端右鍵選單項目
- 透過外掛設定讀寫鉤子儲存自己的設定
- 透過 `setLanguage()` 與 `retranslateUi()` 實作多語言支援

以下是一個最簡單的示例：

```c++
#include "plugininterface.h"

#include <QMap>
#include <QMessageBox>
#include <QDebug>

#define PLUGIN_NAME    "Hello World"
#define PLUGIN_VERSION "0.0.1"

class HelloWorld : public PluginInterface
{
	Q_OBJECT
	Q_PLUGIN_METADATA(IID "org.quardCRT.PluginInterface" FILE "../plugininterface.json")
	Q_INTERFACES(PluginInterface)

public:
	HelloWorld() : m_action(nullptr) {}
	virtual ~HelloWorld() {}

	int init(QMap<QString, QString> params, QWidget *parent) {
		foreach (QString key, params.keys()) {
			qDebug() << key << " : " << params[key];
		}
		qDebug() << "Hello World init";
		m_action = new QAction("Hello World", parent);
		connect(m_action, &QAction::triggered, [parent](){
			QMessageBox::information(parent, "Hello World", "Hello World");
		});

		return 0;
	}

	void setLanguage(const QLocale &language,QApplication *app) {Q_UNUSED(language);Q_UNUSED(app);}
	void retranslateUi() {}
	QString name() { return PLUGIN_NAME; }
	QString version() { return PLUGIN_VERSION; }

	QMap<QString,void *> metaObject() {
		QMap<QString,void *> ret;
		ret.insert("QAction", (void *)m_action);
		return ret;
	}

	QMenu *terminalContextMenu(QString selectedText, QString workingDirectory, QMenu *parentMenu) {Q_UNUSED(selectedText);Q_UNUSED(workingDirectory);Q_UNUSED(parentMenu); return nullptr;}
	QList<QAction *> terminalContextAction(QString selectedText, QString workingDirectory, QMenu *parentMenu) {Q_UNUSED(selectedText);Q_UNUSED(workingDirectory);Q_UNUSED(parentMenu); return QList<QAction *>();}

private:
	QAction *m_action;
};
```

### 模板工程

對於新的外掛開發，建議使用 GitHub 模板工程 [plugin-template](https://github.com/QuardCRT-platform/plugin-template)。

該模板已包含：

- 外掛開發所需的專案結構
- 建構腳本與工程配置
- 基於 GitHub Actions 的 CI 設定

這樣你可以把更多精力放在外掛邏輯本身，而不是從零建立專案骨架。

### 相容性說明

建構外掛時，請留意以下幾點：

- 外掛必須匹配執行中 quardCRT 所期望的外掛 API 版本
- 外掛是原生二進位，因此編譯器、Qt 版本、架構與平台相容性都很重要
- 如果外掛依賴額外共享函式庫，這些函式庫在執行階段也必須可用

如果一個外掛看起來沒問題但仍然無法載入，外掛資訊視窗通常是第一個排查位置。

## 範例

目前 quardCRT 已有一些開源外掛，可作為開發參考：

- [plugin-SearchOnWeb](https://github.com/QuardCRT-platform/plugin-SearchOnWeb)

為終端右鍵選單加入搜尋動作，可將選中文本快速送到 Google、Bing、百度、GitHub 等服務。

- [plugin-quickcomplete](https://github.com/QuardCRT-platform/plugin-quickcomplete)

提供使用者自訂命令，用於快速傳送到目前工作階段。

- [plugin-onestep](https://github.com/QuardCRT-platform/plugin-onestep)

提供預填 SSH 資訊與更高效的主機選擇流程，在嵌入式開發或裝置初始化場景中較為實用。

## 更多

若想了解更多資訊、模板與相關倉庫，請參考 quardCRT 外掛開放平台：

- [https://github.com/QuardCRT-platform](https://github.com/QuardCRT-platform)

外掛系統仍在持續演進中。如果你對外掛 API、擴充點或開發者工具有想法，歡迎在 GitHub 或 Gitee 上提交 issue 或 discussion。
