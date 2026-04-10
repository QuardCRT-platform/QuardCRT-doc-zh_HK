<div style="text-align: right"><a href="../../en/latest/changelog.html">🇺🇸 English</a> | <a href="../../zh-cn/latest/changelog.html">🇨🇳 简体中文</a> | <a href="../../zh-tw/latest/changelog.html">🇭🇰 繁體中文</a> | <a href="../../ja/latest/changelog.html">🇯🇵 日本語</a></div>

# 更新日誌

## [[待發佈](https://github.com/QQxiaoming/quardCRT)]

## [[V0.6.0](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.6.0)] - 2026-04-10

- 修復主視窗錯誤拋出的問題
- 增加日誌中允許加入自訂資料的功能
- 改進記錄日誌檔案路徑設定選項
- 在設定中增加 TFTP 伺服器配置
- 增加終端錄製影片功能
- Raw 協議增加四種模式：TCP Client、TCP Server、UDP Send、UDP Receive
- 增加查看自身 log 視窗的功能，用於 quardCRT 自身除錯
- 改進 TFTP 協議邏輯
- 支援 Emoji 中旗幟符號的顯示
- 改進終端內容匹配功能
- 修復 Linux 下在特定字元場景中終端卡死的問題
- 修復 Linux 下序列埠驅動不支援 Break 時無法開啟序列埠的問題
- 修復浮動視窗關閉後部分資源未正確釋放的問題 [#50](https://github.com/QQxiaoming/quardCRT/issues/50)

## [[V0.5.1](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.5.1)] - 2024-09-26

- Windows 下如果 Profile 不存在，則自動使用預設配置
- 增加連接列 ToolTip 顯示
- 增加系統響鈴支援
- 增加錄製腳本功能
- 增加最近載入的腳本功能
- 增加停用外掛命令列選項
- 增加浮動視窗關閉時二次確認
- 改進記錄日誌等預設路徑為上次儲存路徑
- 改進工作階段標籤外觀
- 修復可能存在的小機率記憶體洩漏問題
- 更新預構建外掛 [ListSerial](https://github.com/QuardCRT-platform/plugin-ListSerial) 到 V0.0.5 版本

## [[V0.5.0](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.5.0)] - 2024-08-26

- 為腳本功能加入 Python 腳本引擎 [#31](https://github.com/QQxiaoming/quardCRT/pull/31)
- 增加選擇行尾序列功能
- 增加狀態列日誌資訊與 SSH 加密演算法資訊
- 分割畫面模式下啟用的工作階段增加強調色邊框
- 高亮功能增加自訂顏色功能
- 多行貼上確認時允許編輯待貼上文字
- 標籤列標題允許顯示自訂工作階段名稱
- Windows 增加自訂 Local Shell Profile 路徑功能
- 修復分割畫面模式下某些情況點擊新增標籤按鈕時，工作階段未正確建立或出現在錯誤標籤群組的問題
- 修復 SSH 連線在部分情況下無法透過按 Enter 發起重連的問題
- 修復鎖定或解鎖工作階段時目標工作階段物件不準確的問題
- 修復浮動視窗內容選單中部分功能無法使用的問題
- 修復不同情況下新建工作階段名稱不一致的問題 [#45](https://github.com/QQxiaoming/quardCRT/issues/45)
- 更新預構建外掛 [timestamp](https://github.com/QuardCRT-platform/plugin-timestamp) 到 V0.0.3 版本

## [[V0.4.8](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.8)] - 2024-07-26

- 增加回顯功能
- 修復部分工作階段類型無法重連的問題
- 增加非連線狀態下的工作階段可透過單擊 Enter 自動重連功能
- 增加序列埠自動檢測實體連線中斷功能
- 在選擇序列埠頁面中增加重新整理序列埠按鈕
- 增加最多四視窗分割畫面模式以及多種版面配置模式
- 傳送命令視窗增加單工作階段、群組工作階段、全部工作階段三種模式
- 外掛資訊頁面增加外掛網站主頁顯示
- 增加通知中心
- 增加內部命令視窗
- 改進 URL 識別連結的內容選單
- 改進查找視窗，每次開啟時自動填入目前選取的文字
- 改進狀態列
- 修復非英文環境下 Telnet 工作階段儲存配置錯誤導致無法連線的問題 [#IAADHZ](https://gitee.com/QQxiaoming/quardCRT/issues/IAADHZ)
- 新增預構建外掛 [timestamp](https://github.com/QuardCRT-platform/plugin-timestamp)，更新預構建外掛 [ListSerial](https://github.com/QuardCRT-platform/plugin-ListSerial) 到 V0.0.3 版本，更新預構建外掛 [CharacterCode](https://github.com/QuardCRT-platform/plugin-CharacterCode) 到 V0.0.4 版本

## [[V0.4.7](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.7)] - 2024-06-26

- 增加廣播工作階段功能 [#36](https://github.com/QQxiaoming/quardCRT/issues/36)
- 增加標籤標記顏色功能
- 增加區塊選擇（Shift+click）與列選擇（Alt+Shift+click）功能
- 增加使用者自訂游標顏色設定
- 增加設定中可選項目的工具提示
- 增加高級選項，可設定預設啟動本地終端所使用的 Shell（Linux/MacOS 下預設為 $SHELL，Windows 下預設為系統內建 PowerShell；Windows 下此功能僅用於調整 PowerShell 版本，而非啟動其他 Shell，其他 Shell 請使用本地 Shell 工作階段設定特定命令啟動）
- 修復修改目前執行中的工作階段配置導致崩潰的問題
- 修復多螢幕情況下內容選單彈出位置錯誤的問題
- 修改為右鍵點擊非目前標籤頁時自動切換到該標籤頁
- 修復 Windows MSVC 版本 local shell 游標對齊錯誤問題，需要停用 resizeQuirk [#39](https://github.com/QQxiaoming/quardCRT/issues/39)
- 修復多行文字貼上確認無效問題，並允許使用者自行設定啟用或停用
- 修復自動修剪貼上文字內容中空白行的問題，並允許使用者自行設定啟用或停用
- 修復 SSH 初始化終端大小不穩定的問題 [#40](https://github.com/QQxiaoming/quardCRT/issues/40)
- 修復 SSH 遠端主動結束後小機率崩潰的問題
- 修復將字型設定恢復為內建字型時顯示異常的問題
- 修復 Linux 多螢幕環境下，視窗移動或調整大小操作導致視窗位置異常的問題
- 新增整合預構建外掛 [TextStatistics](https://github.com/QuardCRT-platform/plugin-TextStatistics)，更新預構建外掛 [CharacterCode](https://github.com/QuardCRT-platform/plugin-CharacterCode) 到 V0.0.3 版本

## [[V0.4.6](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.6)] - 2024-05-26

- 增加設定主介面主題色功能
- 增加狀態列顯示工作階段資訊功能
- 在 Windows 增加啟動 WSL 終端工具列按鈕
- 增加使用者自訂外掛載入路徑設定
- 修復某些 shell 環境下複製標籤時工作目錄未能正確複製的問題
- 修復鍵盤綁定設定中取消修改時仍會被儲存的問題
- 修復關閉全部標籤頁時確認對話框無法選擇取消的問題
- 修復工作階段管理器中修改工作階段屬性後，目前選中的工作階段被錯誤切換的問題
- 修復新工作階段可能建立在被隱藏標籤群組上的問題
- 新增整合預構建外掛 [CharacterCode](https://github.com/QuardCRT-platform/plugin-CharacterCode)、[ListSerial](https://github.com/QuardCRT-platform/plugin-ListSerial)，更新預構建外掛 [SearchOnWeb](https://github.com/QuardCRT-platform/plugin-SearchOnWeb) 到 V0.0.4 版本

## [[V0.4.5](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.5)] - 2024-04-26

- 將終端文字被選中後的強調色透明度改為 50%，而非原本的 100%
- 修復渲染符號 `×`、`÷`、`‖` 寬度異常的問題
- 修復極小機率下程式崩潰的問題
- 修復游標定位問題 [#I8RB90](https://gitee.com/QQxiaoming/quardCRT/issues/I8RB90)
- 移除對 Qt 中 core5compat 的依賴（參考 qtermwidget 上游 pr，但有修改）
- 禁止使用中鍵滾動檢視歷史資訊（參考 qtermwidget 上游 pr，但有修改）
- 修復部分符號渲染寬度異常的問題
- 增加 ANSI OSC52 sequence 支援
- 修復中斷工作階段時會直接關閉標籤而非斷開工作階段的問題
- 修復切換語言時快速連線視窗部分 UI 未能重新整理的問題
- 改進工作階段管理器頁面寬度可自由調整
- Windows 下 MSVC 建構版本採用 ConPty 取代 WinPty，Mingw 建構版本則繼續使用 WinPty
- 改進雙擊選取 CJK 字元時的表現
- 改進輸入法預編輯區域的顯示效果
- 增加終端配色方案調色盤設定功能
- 增加切換主題時自動切換終端配色方案功能
- 增加刪除工作階段時的確認對話框
- 修復內容選單過長時顯示不全難以操作的問題
- 修復 Windows 下一些主題切換造成的顯示異常問題
- 更新預構建外掛 [onestep](https://github.com/QuardCRT-platform/plugin-onestep) 到 V0.0.3 版本

## [[V0.4.4](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.4)] - 2024-03-26

- 增加 ASCII 發送/接收、Kermit 發送/接收、xyzmodem 發送/接收功能
- 修復啟動 TFTP 選單項目指示的狀態可能出現錯誤問題
- 修復終端顯示超過第一平面的 Unicode 字元時程式崩潰的問題
- 修復 Linux 上拖拽視窗到螢幕邊緣觸發視窗大小調整後，終端介面渲染不重新整理的問題

## [[V0.4.3](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.3)] - 2024-02-26

- 終端連結增加 tooltip，並在按下 Ctrl 後修改滑鼠形狀
- 修改 macOS 上預設 LC_CTYPE 設定為 UTF-8，其他平台不做預設配置，可透過設定檔修改是否啟用
- 修復 macOS 上預構建版本遺漏打包部分翻譯檔案的問題
- 修復 Linux 上最大化視窗時終端介面渲染未及時重新整理的問題
- 外掛系統完成多語言支援
- 部分 UI 細節美化
- 新增一個新的說明文件介面
- 增加德語、葡萄牙語（巴西）、捷克語、阿拉伯語支援

## [[V0.4.2](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.2)] - 2024-01-28

- 全螢幕模式下增加 ESC 退出全螢幕功能
- 外掛平台支援動態啟用或停用外掛功能
- 優化解決軟體啟動後固定占用 CPU 負載的問題
- 優化 Windows 下本地終端上下搜尋歷史命令時游標位置錯誤問題
- 修復 tftpserver 可能的錯誤 ack 處理問題
- 修復 macOS 下全螢幕導致程式崩潰問題
- 修復 macOS native UI 模式下標題按鈕沒有切換為 macOS 風格的問題
- 修復 macOS 使用 native UI 樣式標題按鈕全螢幕後，無法顯示介面內容選單中退出全螢幕選項的問題
- 預構建版本增加對於 [外掛生態平台](https://github.com/QuardCRT-platform) 的預構建外掛打包，首次包含外掛 [SearchOnWeb](https://github.com/QuardCRT-platform/plugin-SearchOnWeb)、[onestep](https://github.com/QuardCRT-platform/plugin-onestep)、[quickcomplete](https://github.com/QuardCRT-platform/plugin-quickcomplete)

## [[V0.4.1](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.1)] - 2024-01-13

- 增加工作階段管理器中於新視窗開啟工作階段功能
- 增加設定標籤頁加號按鈕模式，可選為新建工作階段、複製工作階段、本地 Shell 工作階段三種方式
- 增加工作階段管理器中的篩選功能
- 修復拖拽標籤時預覽視窗存在導致視窗閃爍的問題

## [[V0.4.0](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.4.0)] - 2023-12-20

- 主 UI 全面更新，整體風格更現代化，配套亮色與暗色主題更加美觀
- 增加設定選項中開啟目前設定檔功能
- 右上角增加實驗室功能，SSH 掃描遷移至實驗室，開放外掛介面以增加更多特定功能到實驗室，參見 [外掛平台](https://github.com/QuardCRT-platform)
- SFTP 視窗增加書籤功能，改進 SFTP 操作邏輯
- 改進與優化 HexView 視窗
- 改進工作階段複製功能，可複製的工作階段類型（SSH、Telnet 等）直接複製，不可複製的工作階段類型（序列埠等）會彈出工作階段設定視窗
- 改進拖拽標籤時的樣式，滑鼠可正確顯示為抓握手勢
- 修復開啟工作階段屬性時存在歷史頁面未重新整理的問題
- 修復工作階段內 line 字元渲染錯誤
- 修復開啟 SSH 工作階段後，在未變更視窗大小的情況下，預設終端大小不正確
- 修復切換主題時 Tab Add New 按鈕樣式未更新
- 修復終端配色方案修改後無法持久保存 [#I8PLTP](https://gitee.com/QQxiaoming/quardCRT/issues/I8PLTP)

## [[V0.3.1](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.3.1)] - 2023-12-05

- 增加密碼輸入框支援顯示與隱藏功能
- 增加常用鮑率提示
- 增加右鍵選單請求翻譯功能
- 增加實用工具，用於掃描本地網路 SSH 服務
- SFTP 檔案傳輸視窗增加傳輸進度顯示
- 增加 VNC 協議支援
- 修復二次編輯儲存序列埠工作階段 port 資訊後無法正確連線的問題
- 修復鑰匙圈授權失敗時使用錯誤訊息的問題
- 修復連接埠輸入框最大值錯誤導致無法正確保存工作階段資訊的問題

## [[V0.3.0](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.3.0)] - 2023-11-28

- 增加 SSH2 協議支援（目前僅支援密碼驗證，使用者密碼儲存在本地系統鑰匙圈中，不儲存在本軟體配置檔中）
- 增加 SSH2 工作階段開啟 SFTP 檔案傳輸視窗功能
- 增加自訂設定單字字元（Word Characters）功能，可設定哪些字元視為單字字元，方便快速選取單字
- 增加雙擊工作階段管理器內工作階段進行連線功能
- 增加工作階段管理器關閉按鈕
- 修復修改工作階段屬性後工作階段管理器內排序重新排列問題
- 修復序列埠連線正常但彈出錯誤提示 “No Error” 的問題
- 修復連線失敗的工作階段無法關閉的問題

## [[V0.2.6](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.2.6)] - 2023-11-15

- 增加標籤卡懸浮預覽功能
- Windows 本地終端增強，現在可以像 Linux 一樣使用 Tab 鍵選擇補全命令
- 增加工作階段狀態查詢，可透過工作階段設定或屬性中的狀態查看工作階段狀態，目前僅支援本地 Shell 工作階段查詢程序資訊
- 終端內容匹配支援路徑匹配，可右鍵快速開啟檔案或目錄
- 增加高亮顯示匹配內容功能
- 修復中文全形引號渲染位置錯誤的問題
- 修復 macOS 錯誤綁定了複製貼上快捷鍵，導致無法 kill 終端內程序的問題
- 增加更多語言（西班牙語、法語、韓語、俄語、繁體中文）支援（由 GitHub Copilot 提供）

## [[V0.2.5](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.2.5)] - 2023-11-09

- 增加浮動視窗模式，且支援移回主視窗
- 增加標籤頁自由拖拽（拖拽成浮動視窗或拖拽至分割畫面）
- 修復移動標籤後可能導致的嚴重崩潰問題與標籤標題顯示錯誤問題
- 增加高級設定中選擇 UI 樣式為原生風格（單平台使用者可能希望使用原生風格，多平台使用者可能希望使用統一風格）
- 增加設定中一鍵清理已選背景圖片功能
- 優化離開應用或關閉工作階段時的二次確認功能，現在本地 Shell 工作階段會根據是否有子程序決定是否需要二次確認，其他工作階段類型不變
- 增加設定標籤標題模式，可選擇以簡要、完整、滾動三種方式顯示工作階段標題

## [[V0.2.4](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.2.4)] - 2023-11-03

- 增加 Windows 上 NamedPipe 協議支援（Linux/macOS 上對應 unix domain socket）
- 修復 Windows 上無法啟動印表機服務問題
- 修復關閉標籤頁時部分記憶體未釋放的問題
- 增加離開應用或關閉工作階段時需要二次確認功能
- 增加工作階段連線狀態顯示功能（標籤頁以圖示形式顯示）
- 增加設定終端字型功能
- 增加設定終端回捲行數功能
- 增加設定游標形狀和閃爍功能
- 終端背景支援 Gif 動畫格式檔案（需在高級設定中啟用動畫支援）
- 終端背景支援 mp4、avi、mkv、mov 影片格式檔案（需在高級設定中啟用動畫支援）
- 更新全域設定介面，分類顯示設定項
- 增加工作階段設定介面，現在可修改與編輯工作階段屬性
- 增加分離啟動新視窗功能
- 增加軟體自身除錯資訊日誌系統，使用者預設不開啟，必須手寫 config 檔才會啟動

## [[V0.2.3](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.2.3)] - 2023-10-26

- 修復錯誤 CI 環境，與 V0.2.2 無實質改動

## [[V0.2.2](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.2.2)] - 2023-10-26

- 修復工作階段資訊保存錯誤導致右側工作階段管理器中無法正確連線工作階段的問題 [#I8AJN1](https://gitee.com/QQxiaoming/quardCRT/issues/I8AJN1)
- 快速連線支援選擇僅開啟工作階段與僅儲存工作階段
- 改進書籤管理功能
- 實作保存設定與即時保存設定按鈕功能
- 增加 ALT+'-' 與 ALT+'=' 全域快捷鍵切換目前標籤
- 增加 ALT+'{num}' 全域快捷鍵切換到指定標籤
- 增加 ALT+LEFT、ALT+RIGHT 全域快捷鍵映射到 home 與 end 按鍵（考慮 macbook 沒有 home 和 end 按鍵）
- 增加高清截圖目前終端功能
- 增加匯出目前終端工作階段內容（pdf/txt）功能
- 增加印表機列印目前終端工作階段功能
- 增加鎖定工作階段功能
- 增加配置啟動新的本地終端預設工作路徑
- 終端背景圖片支援平鋪模式
- 持久化儲存主介面版面資訊
- 優化介面內容選單
- 優化開啟檔案對話框 UI
- 修改 Windows 上渲染粗體字型導致游標異常，暫時不支援粗體渲染以保證游標位置正確
- 修復 Windows 上執行命令後設定的工作路徑不正確問題
- 增加 macOS 上 cmd+delete 作為 delete 按鍵功能（因為通常 macOS 上 delete 鍵為 backspace）

## [[V0.2.1](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.2.1)] - 2023-10-19

- Linux 打包 fcit 外掛以支援更多中文輸入法
- Linux 修復中文字元渲染游標錯誤
- 修復 HEX 檢視格式渲染錯誤與資料獲取失敗問題
- 持久化儲存工作階段資訊

## [[V0.2.0](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.2.0)] - 2023-10-18

- 增加使用 alt+n/alt+J 切換簡約/標準 UI
- 增加啟動 TFTP 伺服器實用功能
- 優化 hex view 顯示介面
- Windows 安裝程式增加使用 quardCRT 開啟的系統整合右鍵選單
- 標籤列右鍵選單增加多個實用功能
- 修復 Windows 上中文等其他寬字元游標位置錯誤
- 增加配置終端背景圖片功能
- 增加目錄書籤功能
- 增加持久儲存使用者設定功能
- 修復一些 UI 細節錯誤
- 修復一些小機率可能崩潰的問題

## [[V0.1.5](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.1.5)] - 2023-10-09

- 增加終端右側捲動條
- 修復 Windows/macOS 上滑鼠中鍵不能執行複製並貼上的問題
- 增加雙終端工作階段分割畫面顯示
- 增加簡約 UI 介面選項

## [[V0.1.4](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.1.4)] - 2023-10-08

- 增加側邊欄工作階段管理器
- 增加狀態列提示資訊
- 增加命令輸入列
- 完善快捷鍵功能
- 修復工作階段複製時工作路徑不一致的問題
- 增加終端 URL 內容動態解析
- 修復可能的崩潰問題

## [[V0.1.3](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.1.3)] - 2023-09-29

- 再次修復 Windows 存在無法啟動的問題（V0.1.0 引入）（此版本徹底修復了 V0.1.0 問題）

## [[V0.1.2](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.1.2)] - 2023-09-29

- 再次修復 Windows 存在無法啟動的問題（V0.1.0 引入）

## [[V0.1.1](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.1.1)] - 2023-09-29

- 修復 Windows 存在無法啟動的問題（V0.1.0 引入）

## [[V0.1.0](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.1.0)] - 2023-09-29

- 標籤卡名稱可雙擊切換長/短名稱
- 增加儲存 log 功能
- 增加快速開啟本地 Shell 快捷鍵與複製工作階段快捷鍵
- 增加 Windows 下感知目前即時工作路徑（像 Linux 和 macOS 一樣的體驗）
- 增加 HEX 檢視器

## [[V0.0.2](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.0.2)] - 2023-09-27

- 主介面增加選單列、工具列，完善更多右鍵選單
- 增加更多終端介面配色風格
- 增加動態切換語言功能
- 增加動態切換主題功能

## [[V0.0.1](https://github.com/QQxiaoming/quardCRT/releases/tag/V0.0.1)] - 2023-09-26

- 實作主介面終端功能
- 增加標籤卡分頁管理
- 支援 telnet 協議
- 支援序列埠協議
- 支援 RAW 協議
- 支援本地 Shell
- 介面支援簡體中文、英文、日文