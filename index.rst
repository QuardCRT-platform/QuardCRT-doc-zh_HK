.. raw:: html

   <div style="text-align: right"><a href="../../en/latest/index.html">🇺🇸 English</a> | <a href="../../zh-cn/latest/index.html">🇨🇳 简体中文</a> | <a href="../../zh-tw/latest/index.html">🇭🇰 繁體中文</a> | <a href="../../ja/latest/index.html">🇯🇵 日本語</a></div>

quardCRT
----------------------------------

.. image:: https://img.shields.io/github/actions/workflow/status/qqxiaoming/quardCRT/windows.yml?branch=main&logo=windows
   :target: https://github.com/QQxiaoming/quardCRT/actions/workflows/windows.yml
   :alt: Windows ci
.. image:: https://img.shields.io/github/actions/workflow/status/qqxiaoming/quardCRT/linux.yml?branch=main&logo=linux
   :target: https://github.com/QQxiaoming/quardCRT/actions/workflows/linux.yml
   :alt: Linux ci
.. image:: https://img.shields.io/github/actions/workflow/status/qqxiaoming/quardCRT/macos.yml?branch=main&logo=apple
   :target: https://github.com/QQxiaoming/quardCRT/actions/workflows/macos.yml
   :alt: Macos ci
.. image:: https://img.shields.io/codefactor/grade/github/qqxiaoming/quardCRT.svg?logo=codefactor
   :target: https://www.codefactor.io/repository/github/qqxiaoming/quardCRT
   :alt: CodeFactor
.. image:: https://readthedocs.org/projects/quardcrt/badge/?version=latest
   :target: https://quardcrt.readthedocs.io/en/latest/?badge=latest
   :alt: Documentation Status
.. image:: https://img.shields.io/github/license/qqxiaoming/quardCRT.svg?colorB=f48041&logo=gnu
   :target: https://github.com/QQxiaoming/quardCRT
   :alt: License
.. image:: https://img.shields.io/github/tag/QQxiaoming/quardCRT.svg?logo=git
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

quardCRT是一款終端模擬和遠端桌面軟體，支援多種後端協議，可無依賴地跨平台使用，在windows/linux/mac上具有完全一致的使用者體驗。支援多標籤、歷史管理等傳統終端軟體功能，並支援一些獨特的細節功能。

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

- **跨平台**: Windows, MacOS, Linux
- **多種協議**: SSH, Telnet, Serial, LocalShell, RawSocket, NamedPipe, VNC
- **多會話**: 多標籤，多窗口，多監視器，浮動窗口
- **多語言**: 簡體中文，繁體中文，英語，日語，韓語，西班牙語，法語，俄語，德語，葡萄牙語(巴西)，捷克語，阿拉伯語
- **多主題**: 亮色，暗色
- **會話歷史管理**: 會話歷史管理，會話歷史搜索
- **會話管理**: 會話管理，會話導入導出
- **HEX顯示**: HEX顯示
- **文件傳輸**: SFTP, Xmodem, Ymodem, Zmodem, Kermit
- **腳本**: 腳本錄製，腳本回放
- **終端定制**: 終端字體，顏色，大小，光標，回滾，背景等

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

----------------------------------
插件
----------------------------------

quardCRT將從V0.4.0版本開始支持插件，插件將以Qt插件的形式提供，以動態庫的形式加載，關於插件開發信息的更多了解，請參考插件開放平台 `platform <https://github.com/QuardCRT-platform>`_ 。該平台將提供插件開發的模板倉庫和相關示例。目前插件功能還處於早期開發階段，如果您有好的想法或建議，請在 `GitHub <https://github.com/QQxiaoming/quardCRT>`_ 或 `Gitee <https://gitee.com/QQxiaoming/quardCRT>`_ 上提交issues或討論。

.. toctree::
   :maxdepth: 3
   :caption: 目錄:

   安裝<installation.md>
   使用<usage.md>
   配置<configuration.md>
   常見問題<faq.md>
   貢獻<contributing.md>
   更新日誌<changelog.md>
   許可證<license.md>
   路線圖<roadmap.md>
   致謝<acknowledgements.md>
