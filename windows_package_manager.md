# Windows Package Manager
## chocolately
* 預設會安裝在 %USERPROFILE% 目錄下，若要指定 chocolately 及後續軟體的安裝跟目錄，需先設定環境變數 ChocolateyInstall, ChocolateyToolsLocation，再開始安裝。
* 常用指令
  * choco list --local-only
  * choco upgrade all
## scoop
* 預設會安裝在 %USERPROFILE% 目錄下，若要指定 scoop 及後續軟體的安裝跟目錄，需先設定環境變數 SCOOP, SCOOP_GLOBAL，再開始安裝。
* 常用指令
  * scoop list
  * scoop update
  * scoop update *
  * scoop cleanup *
  * scoop cache rm *
* 自動複製選取文字
  * Session -> Preferences -> Text
  * Automatically copy selection 打勾
* 滑鼠右鍵貼上
  * Session -> Preferences -> Terminal
  * Mouse Actions 的 Right click 選擇 Paste text