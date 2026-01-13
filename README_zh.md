[English](README.md)

# Gemini 無損去水印工具 - [xuss-mt.github.io](https://xuss-mt.github.io/gemini-watermark-remover/)

這是一個高效、100% 本地運行的 Gemini AI 浮水印移除工具。利用純 JavaScript 開發，核心採用數學精確的 **反向 Alpha 混合 (Reverse Alpha Blending)** 演算法，而非不可預測的 AI 修補技術。

## 功能特點

* ✅ **100% 本地處理** - 無後端、無伺服器處理，資料完整保留在你的瀏覽器中。
* ✅ **隱私優先** - 圖片絕不會上傳到任何伺服器，確認資料安全。
* ✅ **數學級精確** - 基於反向 Alpha 混合公式還原，不會像 AI 模型產生像素「幻覺」。
* ✅ **自動偵測** - 智慧辨識 48×48 或 96×96 的浮水印尺寸變體。
* ✅ **操作簡單** - 直覺的拖放介面，即刻讀取並完成處理。
* ✅ **跨平台支援** - 在所有現代網頁瀏覽器上都能流暢執行。

## 範例展示

<details open>
<summary>點擊展開/摺疊範例</summary>
　
<p>無損差異對比</p>
<p><img src="docs/lossless_diff.webp"></p>

| 原始圖片 | 移除浮水印後 |
| --- | --- |
| <img src="docs/1.webp" width="400"> | <img src="docs/unwatermarked_1.webp" width="400"> |
| <img src="docs/2.webp" width="400"> | <img src="docs/unwatermarked_2.webp" width="400"> |
| <img src="docs/3.webp" width="400"> | <img src="docs/unwatermarked_3.webp" width="400"> |

</details>

## ⚠️ 免責聲明

> [!WARNING]
> **使用風險自負**
> 本工具會修改圖片檔案。雖然設計初衷是穩定運行，但仍可能因以下因素產生非預期結果：
> * Gemini 浮水印實作方式的變更
> * 損毀或不常見的圖片格式
> * 未涵蓋的極端情況
> 
> 
> 作者對任何資料遺失、圖片損毀或非預期的修改不負任何責任。利用本工具即代表你已了解並確認這些風險。

## 使用方式

### 線上工具

1. 開啟 [xuss-mt.github.io/gemini-watermark-remover/](https://xuss-mt.github.io/gemini-watermark-remover/)。
2. 拖放或點擊選擇你的 Gemini 生成圖片。
3. 引擎會自動讀取並處理。
4. 下載清理後的圖片。

### Gemini 對話頁面專用腳本 (Userscript)

1. 安裝腳本管理器（如 Tampermonkey 或 Greasemonkey）。
2. 開啟並安裝 [gemini-watermark-remover.user.js](https://www.google.com/search?q=https://xuss-mt.github.io/gemini-watermark-remover/userscript/gemini-watermark-remover.user.js)。
3. 在 Gemini 對話頁面中，點擊「複製圖片」或「下載圖片」即可自動移除浮水印。

## 運作原理

### 浮水印合成流程

Gemini 利用標準的 Alpha 合成技術套用浮水印：

其中：

* `watermarked`: 帶有浮水印的像素值。
* `α`: Alpha 通道值 (0.0 - 1.0)。
* `logo`: 浮水印圖示顏色值 (白色 = 255)。
* `original`: 我們想要讀取並還原的原圖像素值。

### 反向解法

為了移除浮水印，我們利用代數對 `original` 進行求解：

利用在已知背景上讀取浮水印資源，我們可以重建精確的 Alpha Map，並套用反向公式來無損還原原始像素。

## 法律聲明

本工具僅供 **個人與教育用途** 使用。

移除浮水印可能涉及法律影響，具體取決於你所在地區的司法管轄權及圖片用途。使用者需自行負責確認其行為符合適用法律、服務條款及智慧財產權。

作者不贊成也不鼓勵將此工具用於侵犯版權、欺詐或任何其他違法用途。

**本軟體依「原樣」提供，不提供任何形式的保證。作者在任何情況下均不對因利用本軟體而產生的任何索賠、損害或其他責任負責。**

## 授權協定

[MIT License](https://www.google.com/search?q=./LICENSE)
