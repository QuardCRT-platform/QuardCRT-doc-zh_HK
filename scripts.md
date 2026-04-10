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

## 錄製腳本

quardCRT 可以錄製互動式終端操作，並生成一個可作為起點的 Python 腳本。

在 `腳本` 選單中：

1. 選擇 `開始錄製腳本`。
2. 在目前終端工作階段中進行操作。
3. 選擇 `停止錄製腳本...` 並儲存生成的 `.py` 檔案。

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
