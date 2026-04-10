.. raw:: html

   <div style="text-align: right"><a href="../../en/latest/index.html">🇺🇸 English</a> | <a href="../../zh-cn/latest/index.html">🇨🇳 简体中文</a> | <a href="../../zh-tw/latest/index.html">🇭🇰 繁體中文</a> | <a href="../../ja/latest/index.html">🇯🇵 日本語</a></div>

quardCRT
----------------------------------

.. image:: https://img.shields.io/github/actions/workflow/status/qqxiaoming/quardCRT/windows.yml?branch=main&logo=data:image/svg+xml;base64,PHN2ZyByb2xlPSJpbWciIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48dGl0bGU+V2luZG93czwvdGl0bGU+PHBhdGggZD0iTTAsMEgxMS4zNzdWMTEuMzcySDBaTTEyLjYyMywwSDI0VjExLjM3MkgxMi42MjNaTTAsMTIuNjIzSDExLjM3N1YyNEgwWm0xMi42MjMsMEgyNFYyNEgxMi42MjMiIGZpbGw9IiNmZmZmZmYiLz48L3N2Zz4=
   :target: https://github.com/QQxiaoming/quardCRT/actions/workflows/windows.yml
   :alt: Windows ci
.. image:: https://img.shields.io/github/actions/workflow/status/qqxiaoming/quardCRT/linux.yml?branch=main&logo=linux&logoColor=white
   :target: https://github.com/QQxiaoming/quardCRT/actions/workflows/linux.yml
   :alt: Linux ci
.. image:: https://img.shields.io/github/actions/workflow/status/qqxiaoming/quardCRT/macos_arm64.yml?branch=main&logo=apple
   :target: https://github.com/QQxiaoming/quardCRT/actions/workflows/macos_arm64.yml
   :alt: Macos ci
.. image:: https://img.shields.io/codefactor/grade/github/qqxiaoming/quardCRT.svg?logo=codefactor
   :target: https://www.codefactor.io/repository/github/qqxiaoming/quardCRT
   :alt: CodeFactor
.. image:: https://img.shields.io/readthedocs/quardcrt.svg?logo=readthedocs
   :target: https://quardcrt.readthedocs.io/en/latest/?badge=latest
   :alt: Documentation Status
.. image:: https://img.shields.io/github/license/qqxiaoming/quardCRT.svg?colorB=f48041&logo=gnu
   :target: https://github.com/QQxiaoming/quardCRT
   :alt: License
.. image:: https://img.shields.io/github/v/tag/QQxiaoming/quardCRT?filter=V*&logo=git
   :target: https://github.com/QQxiaoming/quardCRT/releases
   :alt: GitHub tag (latest SemVer)
.. image:: https://img.shields.io/github/downloads/QQxiaoming/quardCRT/total.svg?logo=pinboard
   :target: https://github.com/QQxiaoming/quardCRT/releases
   :alt: GitHub All Releases
.. image:: https://img.shields.io/github/stars/QQxiaoming/quardCRT.svg?logo=github
   :target: https://github.com/QQxiaoming/quardCRT
   :alt: GitHub stars
.. image:: https://img.shields.io/github/forks/QQxiaoming/quardCRT.svg?logo=github
   :target: https://github.com/QQxiaoming/quardCRT
   :alt: GitHub forks
.. image:: https://gitee.com/QQxiaoming/quardCRT/badge/star.svg?theme=dark
   :target: https://gitee.com/QQxiaoming/quardCRT
   :alt: Gitee stars
.. image:: https://gitee.com/QQxiaoming/quardCRT/badge/fork.svg?theme=dark
   :target: https://gitee.com/QQxiaoming/quardCRT
   :alt: Gitee forks

.. image:: ./img/social_preview.jpg
   :align: center
   :alt: quardCRT

quardCRT 是一款面向 Windows、Linux 與 macOS 的跨平台終端模擬器與遠端桌面用戶端。它強調跨平台一致的使用體驗，同時提供現代日常終端工具常見的能力，例如多分頁工作流程、工作階段管理、檔案傳輸、主題切換、介面語言切換，以及持續擴展中的外掛生態。

quardCRT 的設計目標，是讓使用者可以低門檻開始使用，同時又具備足夠能力應付日常開發、嵌入式除錯、伺服器維護與輕量級遠端桌面工作。

----------------------------------
快速開始
----------------------------------

1. 閱讀 :doc:`安裝指南 <installation>`，選擇與你平台相符的安裝包。
2. 依照 :doc:`使用指南 <usage>` 熟悉主介面佈局、快速連線流程與常見操作。
3. 使用 :doc:`配置指南 <configuration>` 調整外觀、終端行為、傳輸目錄與高級選項。

----------------------------------
quardCRT 提供什麼
----------------------------------

- 在 Windows、Linux、macOS 上提供大致一致工作流程的跨平台桌面用戶端
- 在單一應用中整合常見終端與遠端存取協議
- 已儲存工作階段、分頁工作流程、分割版面與浮動視窗
- 支援 SFTP、Xmodem、Ymodem、Zmodem、Kermit 的檔案傳輸能力
- 面向使用者的字型、配色、游標、回捲緩衝區、背景媒體等自訂能力
- 多語言介面與外掛擴充能力

.. list-table:: 
   :widths: 33 33 33
   :header-rows: 0

   * - .. image:: ./img/windows.png
          :align: center
          :height: 160px
     - .. image:: ./img/macos.png
          :align: center
          :height: 160px
     - .. image:: ./img/linux.png
          :align: center
          :height: 160px
   * - Windows
     - MacOS
     - Linux

----------------------------------
功能
----------------------------------

- **跨平台**: Windows、macOS、Linux
- **協議**: SSH、Telnet、Serial、Local Shell、Raw Socket、Named Pipe、VNC
- **工作階段工作流程**: 多分頁、多視窗、分割畫面、浮動視窗
- **語言**: 英語、簡體中文、繁體中文、日語、韓語、西班牙語、法語、俄語、德語、葡萄牙語（巴西）、捷克語、阿拉伯語
- **主題**: 亮色與暗色
- **工作階段歷史**: 歷史保存與快速搜尋
- **工作階段管理**: 建立、儲存、整理、匯入、匯出工作階段
- **HEX 顯示**: 以十六進位檢視終端輸出
- **檔案傳輸**: SFTP、Xmodem、Ymodem、Zmodem、Kermit
- **終端自訂**: 字型、顏色、游標、回捲、背景圖片或影片等

----------------------------------
特別功能
----------------------------------

- 標籤浮動預覽
- 支持浮動窗口，標籤拖拽到浮動窗口
- SSH2會話一鍵打開SFTP文件傳輸窗口
- 工作目錄書籤
- 自動發送
- 終端背景圖支持gif動畫和視頻
- 終端關鍵字高亮匹配
- 選中文本翻譯功能
- 路徑匹配一鍵直達
- 工作路徑直達
- Windows本地終端增強（Tab鍵選擇完整命令等）
- 廣播會議
- 會話標籤標記顏色
- 區塊選擇（Shift+點擊）和列選擇（Alt+Shift+點擊）

----------------------------------
文件導讀
----------------------------------

- :doc:`安裝 <installation>`：下載來源、安裝包選擇與平台安裝步驟
- :doc:`使用 <usage>`：介面概覽、第一次上手操作、選單與工具列說明
- :doc:`配置 <configuration>`：全域選項、工作階段行為、儲存位置與高級設定
- :doc:`腳本 <scripts>`：腳本功能使用方式與 API 概覽
- :doc:`外掛 <plugins>`：外掛體系、模板工程與參考範例
- :doc:`常見問題 <faq>`：授權、隱私與常見問答

----------------------------------
插件
----------------------------------

quardCRT 從 V0.4.0 開始支援外掛。外掛以 Qt 外掛形式提供，並以動態函式庫方式載入。若想了解外掛開發資源、模板與範例，請參考外掛 `platform <https://github.com/QuardCRT-platform>`_。如果你對外掛系統有想法或建議，歡迎在 `GitHub <https://github.com/QQxiaoming/quardCRT>`_ 或 `Gitee <https://gitee.com/QQxiaoming/quardCRT>`_ 上提交 issue 或 discussion。

----------------------------------
從商店安裝
----------------------------------

.. image:: https://get.microsoft.com/images/zh-tw%20dark.svg
   :target: https://apps.microsoft.com/detail/quardCRT/9p6102k9qb3t?mode=direct
   :alt: Microsoft Store

- .. image:: https://www.spark-app.store/assets/favicon-96x96-BB0Q9LsV.png
   :target: https://spk-resolv.spark-app.store/?spk=spk://store/development/quardcrt
   :alt: Spark Store

----------------------------------
捐赠
----------------------------------

如果你覺得 quardCRT 對你有幫助，可以透過捐贈支持專案持續開發。

.. list-table:: 
   :widths: 33 33 33
   :header-rows: 0

   * - .. image:: ./img/donate/paypal.jpg
          :align: center
     - .. image:: ./img/donate/alipay.jpg
          :align: center
     - .. image:: ./img/donate/wechat.jpg
          :align: center
   * - paypal
     - alipay
     - wechat

.. toctree::
   :maxdepth: 3
   :caption: 目錄:

   安裝<installation.md>
   使用<usage.md>
   配置<configuration.md>
   腳本<scripts.md>
   插件<plugins.md>
   常見問題<faq.md>
   貢獻<contributing.md>
   更新日誌<changelog.md>
   許可證<license.md>
   路線圖<roadmap.md>
   致謝<acknowledgements.md>
   隱私<privacy.md>
