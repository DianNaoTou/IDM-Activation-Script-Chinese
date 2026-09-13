# IDM 啟用指令碼（繁體中文版）

這是 [IDM Activation Script](https://github.com/lstprjct/IDM-Activation-Script) 的繁體中文翻譯版本，用於管理 Internet Download Manager（IDM）的啟用與試用狀態。

> [!WARNING]
> 本專案僅提供繁體中文翻譯。請自行確認使用方式符合所在地區的法律及 IDM 授權條款。

## 專案來源

- 原始英文版：[lstprjct/IDM-Activation-Script](https://github.com/lstprjct/IDM-Activation-Script)
- 簡體中文版：[cjhdevact/IDM-Activation-Script-Chinese](https://github.com/cjhdevact/IDM-Activation-Script-Chinese)
- 繁體中文版：[DianNaoTou/IDM-Activation-Script-Chinese](https://github.com/DianNaoTou/IDM-Activation-Script-Chinese)

本專案並非原始指令碼作者所建立；繁體中文版是在簡體中文版的基礎上翻譯及整理而成。感謝原作者、翻譯者與所有貢獻者。

## 功能

- 使用登錄檔項目鎖定方式管理 IDM 的試用及啟用狀態
- 安裝 IDM 更新後仍可保留既有狀態
- 重設 IDM 的啟用及試用狀態
- 完全開放原始碼
- 以可檢視的批次指令碼執行

## 版本資訊

目前版本：v1.2（繁體中文版）

## 下載與使用

1. 從 [GitHub 下載 ZIP 檔案](https://github.com/DianNaoTou/IDM-Activation-Script-Chinese/archive/refs/heads/main.zip)。
2. 在下載的 ZIP 檔案上按一下滑鼠右鍵並解壓縮。
3. 開啟解壓縮後的資料夾，執行 `IAS.cmd`。
4. 依照畫面指示選擇所需功能。

建議先安裝乾淨的 [Internet Download Manager](https://www.internetdownloadmanager.com/)，並移除先前使用的修改或修補程式。

> [!NOTE]
> 原始 v1.2 指令碼註明，「啟用」選項可能無法對所有使用者生效，原作者建議改用「凍結試用」選項。

## PowerShell 啟動方式

1. 在 Windows 開始功能表上按一下滑鼠右鍵。
2. 開啟 PowerShell 或終端機（不是命令提示字元）。
3. 執行本專案提供的 `IAS.ps1`。
4. 依照畫面指示操作。

## 選項說明

### 凍結試用

IDM 提供 30 天試用期。此選項會鎖定試用狀態，使試用天數不再遞減。套用時需要網際網路連線；安裝 IDM 更新後通常不必再次執行。

### 啟用

> 原始 v1.2 指令碼標示此功能可能無法正常運作。

此選項使用登錄檔鎖定方式管理 IDM 啟用狀態。執行時需要網際網路連線；若日後再次出現啟用提示，可重新執行此選項。

### 重設啟用／試用狀態

此選項會重設 IDM 的啟用及試用狀態，也可用於排除序號或既有狀態異常。

## 系統需求

- Windows 7、8、8.1、10、11，以及相對應的 Windows Server 版本
- PowerShell 啟動方式需要 Windows 8 或更新版本

## 命令列參數

- `/act`：以無人值守模式執行啟用選項
- `/frz`：以無人值守模式執行凍結試用選項
- `/res`：以無人值守模式執行重設選項

## 運作方式

IDM 會將試用及啟用資訊儲存在多個登錄檔項目中。指令碼會找出相關項目，並依照所選功能建立、鎖定或移除項目。完整實作細節可直接檢視 [`IAS.cmd`](IAS.cmd)。

## 疑難排解

- [Chrome 瀏覽器整合修復說明](https://www.internetdownloadmanager.com/register/new_faq/bi9.html)
- [Firefox 瀏覽器整合修復說明](https://www.internetdownloadmanager.com/register/new_faq/bi4.html)

## 更新紀錄

### v1.2

- 恢復啟用選項，並使用隨機產生的名稱、電子郵件地址及金鑰填入註冊資訊。
- 加入功能可能無法對所有使用者生效的警告，並建議使用「凍結試用」。

### v1.1

- 因 IDM 6.42 Build 3 開始對 IAS 啟用方式顯示偽造序號提示，暫時移除啟用選項並改以「凍結試用」取代。
- 改由 PowerShell 停用 CMD 的快速編輯模式，不再修改登錄檔。感謝 @abbodi1406 提供程式碼及 @awuctl 提供構想。
- 合併以 `conhost.exe` 重新啟動指令碼的處理方式。
- 依據 WindowsAddict 版本更新完整程式碼。

### v1.0

- 加入從 Windows 終端機啟動時，以 `conhost.exe` 重新開啟指令碼的功能。
- 修正無法正確取得目前使用者 SID 的問題。

### v0.9

- 修正非系統管理員帳戶無法執行啟用及重設的問題。
- 修正啟用狀態判斷錯誤。
- 改善偽造序號提示的處理方式。
- 改以 PowerShell 掃描及鎖定 IDM 登錄檔項目。
- 加入指令碼更新檢查功能。
- 執行期間暫時停用快速編輯模式，避免誤觸造成暫停。
- 修改 CLSID 登錄檔項目前會先建立備份。
- 加入更多錯誤檢查。

### v0.8

- 將專案移至 GitHub。
- 修正小型問題。
- 刪除大量空白登錄檔項目時顯示說明。

## 畫面截圖

以下為原始英文版提供的參考畫面；繁體中文版介面以實際執行結果為準。

![IAS 主畫面](https://github.com/lstprjct/IDM-Activation-Script/assets/88411318/fafdb481-c497-464f-b1e6-9a4254eaf880)

![IAS 凍結試用畫面](https://github.com/lstprjct/IDM-Activation-Script/assets/88411318/76b36582-8cf4-4d1e-870f-6e8e57c80a87)

## 貢獻者

| 貢獻者 | 貢獻內容 |
|---|---|
| Dukun Cabul | 研究 IDM 試用重設及啟用邏輯，並製作 [IDM-AIO_2020_Final](https://nsaneforums.com/topic/371047-discussion-internet-download-manager-fixes/page/8/#comment-1632062) AutoIt 工具 |
| AveYo（BAU） | 提供精簡的 [`reg_own` 程式片段](https://pastebin.com/XTPt0JSC) |
| [abbodi1406](https://github.com/abbodi1406) | 協助程式開發 |
| WindowsAddict | 原始 [IAS](https://github.com/WindowsAddict/IDM-Activation-Script) 作者 |
| CJH | 簡體中文版翻譯 |
| DianNaoTou | 繁體中文版翻譯與整理 |

感謝所有 IAS 使用者提供意見、回報及協助。

---

Made with Love ❤️
