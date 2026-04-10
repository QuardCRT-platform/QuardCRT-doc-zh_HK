<div style="text-align: right"><a href="../../en/latest/scripts.html">🇺🇸 English</a> | <a href="../../zh-cn/latest/scripts.html">🇨🇳 简体中文</a> | <a href="../../zh-tw/latest/scripts.html">🇭🇰 繁體中文</a> | <a href="../../ja/latest/scripts.html">🇯🇵 日本語</a></div>

# 腳本

quardCRT 從 V0.5.0 開始支援腳本功能。腳本使用 Python 撰寫，可呼叫 quardCRT 內建 API 來完成終端操作、對話框互動、畫面匹配與檔案傳輸等自動化流程。

本頁先從實際使用角度介紹腳本功能，再給出 API 概覽。

## 腳本適合做什麼

常見用途包括：

- 自動完成裝置或伺服器登入流程
- 等待特定提示字元出現後再送出下一條命令
- 自動化測試步驟或初始化步驟
- 在 quardCRT 內部啟動傳輸任務或小型輔助工作流程
- 透過錄製人工操作生成一份腳本初稿

## 可用性說明

腳本支援依賴於包含 Python 支援的建構版本。如果你的發行版本未整合 Python 執行環境，腳本選單相關功能可能會被停用。

## 執行腳本

透過介面執行 Python 腳本的步驟如下：

1. 開啟 `腳本` 選單。
2. 選擇 `執行...`。
3. 選擇一個 Python 腳本檔案。
4. quardCRT 啟動腳本，並在目前腳本結束或取消之前停用 `執行...`。

當你透過檔案選擇器成功執行一個腳本後，quardCRT 也會將其加入最近腳本清單，方便之後直接從選單再次啟動。

## 取消正在執行的腳本

如果目前有腳本正在執行，可透過 `腳本` 選單中的取消操作停止執行。

這在以下情況下很有用：

- 遠端回應已經偏離預期
- 誤啟動了錯誤腳本
- 腳本等待時間超過預期

## 錄製腳本

quardCRT 可以錄製互動式終端操作，並生成一個可作為起點的 Python 腳本。

在 `腳本` 選單中：

1. 選擇 `開始錄製腳本`。
2. 在目前終端工作階段中進行操作。
3. 選擇 `停止錄製腳本...` 並儲存生成的 `.py` 檔案。

如果你決定不保留本次錄製，可使用 `取消錄製腳本`。

### 錄製腳本通常會生成什麼

生成的 Python 檔案通常會包含：

- `crt.Screen.Synchronous = True`
- 用於傳送輸入的 `crt.Screen.Send(...)`
- 用於等待提示字元或輸出邊界的 `crt.Screen.WaitForString(...)`

這會給你一個可用的起點，但錄製腳本並不保證可直接用於正式環境。實際使用時，通常還需要清理提示字元、改進等待邏輯或刪除不必要的步驟。

## 最近腳本

從檔案選擇器執行過腳本後，quardCRT 會將其記錄到 `腳本` 選單中的最近腳本清單。

如果你想清空這個清單，可以使用 `清空所有最近腳本`。

## 第一個範例

以下是一個最小範例，用於在訊息框中顯示 quardCRT 版本資訊。

```python
import sys
from quardCRT import crt

def main():
	crt.Dialog.MessageBox("quardCRT version is: " + crt.Version)

if __name__ == '__main__':
	main()
```

## API 概覽

quardCRT 的 API 主要包含以下物件：

- `crt`
- `crt.Dialog`
- `crt.Session`
- `crt.Screen`
- `crt.Window`
- `crt.Arguments`
- `crt.Clipboard`
- `crt.FileTransfer`
- `crt.CommandWindow`
- `crt.Tab`

以下章節會繼續詳細說明這些物件。

### crt

`crt` 是 quardCRT 的主要 API，包括以下幾個部分：

#### 方法

- `crt.GetActiveTab() -> object`：獲取目前活動的標籤頁群組。
	- 返回值：Tab 物件。
	- 示例：

		```python
		tab = crt.GetActiveTab()
		```
	- 備註：如果目前沒有活動的 Tab 群組，則獲取第一個 Tab 群組。

- `crt.GetLastError() -> object`：獲取最後一次發生的錯誤。
	- 返回值：Error 物件。
	- 示例：

		```python
		error = crt.GetLastError()
		```

- `crt.GetLastErrorMessage() -> str`：獲取最後一次發生的錯誤訊息。
	- 返回值：錯誤訊息。
	- 示例：

		```python
		message = crt.GetLastErrorMessage()
		```

- `crt.ClearLastError()`：清除最後一次發生的錯誤。
	- 示例：

		```python
		crt.ClearLastError()
		```

- `crt.Sleep(milliseconds: int)`：暫停腳本執行。
	- 參數：
		- `milliseconds`：暫停時間，單位為毫秒。
	- 示例：

		```python
		crt.Sleep(1000)
		```

- `crt.Cmd(cmd: str, [args:list]) -> str`：執行一個 quardCRT 特殊命令。
	- 參數：
		- `cmd`：命令名稱。
		- `args`：命令參數列表。
	- 返回值：命令執行結果。
	- 備註：命令名稱與參數列表請參考 quardCRT 的命令說明。
	- 示例：

		```python
		result = crt.Cmd("show", ["version"])
		```

- `crt.Quit()`：離開 quardCRT。
	- 示例：

		```python
		crt.Quit()
		```

#### 屬性

- `crt.Dialog`：全域對話框物件。
- `crt.Session`：目前工作階段物件。
- `crt.Screen`：目前畫面物件。
- `crt.Window`：全域視窗物件。
- `crt.Arguments`：命令列參數物件。
- `crt.Clipboard`：剪貼簿物件。
- `crt.FileTransfer`：檔案傳輸物件。
- `crt.ScriptFullName`：目前腳本的完整路徑。唯讀。
- `crt.ActivePrinter`：目前活動的印表機名稱。
- `crt.Version`：quardCRT 版本資訊。唯讀。

### Dialog

`Dialog` 用於顯示對話框，全域單例，透過 crt 物件呼叫，例如：

```python
dialog = crt.Dialog
```

包括以下幾個部分：

#### 方法

- `Dialog.MessageBox(message: str, [title: str, buttons: int]) -> int`：顯示一個訊息框。
	- 參數：
		- `message`：訊息內容。
		- `title`：訊息標題。
		- `buttons`：按鈕類型。
	- 返回值：執行結果。0 表示正常，其他值表示異常。
	- 備註：按鈕類型包括 `Dialog.OK`、`Dialog.OK | Dialog.Cancel`、`Dialog.Abort | Dialog.Retry | Dialog.Ignore`、`Dialog.Yes | Dialog.No` 等。
	- 示例：

		```python
		result = crt.Dialog.MessageBox("Hello, quardCRT!", "Message", crt.Dialog.OK)
		```

- `Dialog.Prompt(prompt: str, name: str, input: str, password: bool) -> str`：顯示一個輸入框。
	- 參數：
		- `prompt`：提示內容。
		- `name`：輸入框名稱。
		- `input`：輸入框預設值。
		- `password`：是否為密碼輸入。
	- 返回值：輸入框的值。如果使用者點擊取消，則返回空字串。

- `Dialog.FileOpenDialog(title: str, [buttonLabel: str, directory: str, filter: str]) -> str`：顯示一個開啟檔案對話框。
- `Dialog.FileSaveDialog(title: str, [buttonLabel: str, directory: str, filter: str]) -> str`：顯示一個儲存檔案對話框。

#### 屬性

- `Dialog.OK`：確定按鈕。唯讀。
- `Dialog.Cancel`：取消按鈕。唯讀。
- `Dialog.Abort`：中止按鈕。唯讀。
- `Dialog.Retry`：重試按鈕。唯讀。
- `Dialog.Ignore`：忽略按鈕。唯讀。
- `Dialog.Yes`：是按鈕。唯讀。
- `Dialog.No`：否按鈕。唯讀。

### Session

`Session` 用於管理工作階段，透過 crt 物件呼叫或從 Tab 取得，例如：

```python
session = crt.Session
```

包括以下幾個部分：

#### 方法

- `Session.Connect(cmd: str) -> int`：連線到一個主機。
- `Session.Disconnect()`：中斷目前工作階段。
- `Session.Log(enable: bool)`：啟用或停用日誌記錄。
- `Session.Lock(prompt: str, password: str, lockallsessions: int) -> int`：鎖定工作階段。
- `Session.Unlock(prompt: str, password: str, lockallsessions: int) -> int`：解鎖工作階段。

#### 屬性

- `Session.Connected`：工作階段是否已連線。唯讀。
- `Session.Locked`：工作階段是否已鎖定。唯讀。
- `Session.Logging`：工作階段是否啟用日誌記錄。唯讀。
- `Session.Id`：工作階段的全域 ID。唯讀。

### Screen

`Screen` 用於管理畫面，透過 crt 物件呼叫或從 Tab 取得。

常用方法包括：

- `Screen.WaitForString(...)`
- `Screen.WaitForStrings(...)`
- `Screen.Send(...)`
- `Screen.Clear()`
- `Screen.Get(...)`
- `Screen.Get2(...)`
- `Screen.IgnoreCase(...)`
- `Screen.Print()`
- `Screen.Shortcut(path: str)`
- `Screen.SendKeys(keylist: list[str])`
- `Screen.Screen_ReadString(...)`
- `Screen.WaitForCursor(...)`
- `Screen.WaitForKey(...)`

常用屬性包括：

- `Screen.Synchronous`
- `Screen.CurrentColumn`
- `Screen.CurrentRow`
- `Screen.Rows`
- `Screen.Columns`
- `Screen.IgnoreCase`
- `Screen.MatchIndex`
- `Screen.Selection`
- `Screen.Id`

### Window

`Window` 用於管理應用視窗，全域單例，透過 `crt.Window` 呼叫。

#### 方法

- `Window.Activate()`：啟用視窗。
- `Window.Show(type: int)`：顯示視窗。

#### 屬性

- `Window.State`
- `Window.Active`
- `Window.Hide`
- `Window.ShowNormal`
- `Window.ShowMinimized`
- `Window.ShowMaximized`

### Arguments

`Arguments` 用於取得命令列參數，全域單例，透過 `crt.Arguments` 呼叫。

#### 方法

- `Arguments.GetArg(index: int) -> str`：取得指定索引的參數。

#### 屬性

- `Arguments.Count`：參數數量。唯讀。

### Clipboard

`Clipboard` 用於操作剪貼簿，全域單例，透過 `crt.Clipboard` 呼叫。

#### 屬性

- `Clipboard.Text`：剪貼簿文字。唯讀。

### FileTransfer

`FileTransfer` 用於操作檔案傳輸，全域單例，透過 `crt.FileTransfer` 呼叫。

#### 方法

- `FileTransfer.AddToUploadList(path: str)`：將檔案加入 zmodem 上傳列表。
- `FileTransfer.ClearUploadList()`：清空 zmodem 上傳列表。
- `FileTransfer.ReceiveKermit() -> int`：接收 kermit 檔案。
- `Filetransfer.SendKermit(path: str) -> int`：傳送 kermit 檔案。
- `FileTransfer.ReceiveXmodem(path: str)`：接收 xmodem 檔案。
- `FileTransfer.SendXmodem(path: str) -> int`：傳送 xmodem 檔案。
- `FileTransfer.ReceiveYmodem() -> int`：接收 ymodem 檔案。
- `FileTransfer.SendYmodem(path: str) -> int`：傳送 ymodem 檔案。
- `FileTransfer.SendZmodem() -> int`：傳送 zmodem 檔案。

#### 屬性

- `FileTransfer.DownloadFolder`：下載資料夾。

### CommandWindow

`CommandWindow` 用於操作命令視窗，全域單例，透過 `crt.CommandWindow` 呼叫。

#### 方法

- `CommandWindow.Send()`：傳送文字到命令視窗。

#### 屬性

- `CommandWindow.SendCharactersImmediately`
- `CommandWindow.SendToAllSessions`
- `CommandWindow.Visible`
- `CommandWindow.Text`

### Tab

`Tab` 用於管理標籤頁群組，透過 `crt.GetActiveTab()` 取得。

#### 方法

- `Tab.GetScreen(index: int) -> object`：取得標籤頁群組中的畫面。
- `Tab.GetSession(index: int) -> object`：取得標籤頁群組中的工作階段。
- `Tab.Activate(index: int)`：啟用標籤頁群組中的指定工作階段。

#### 屬性

- `Tab.Number`：標籤頁群組內工作階段數量。唯讀。
