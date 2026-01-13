[中文說明](https://github.com/Xuss-mt/gemini-watermark-remover/blob/main/README_zh.md)

# Gemini Lossless Watermark Remover - [xuss-mt.github.io](https://xuss-mt.github.io/gemini-watermark-remover/)

A high-performance, 100% client-side tool for removing Gemini AI watermarks. Built with pure JavaScript, it leverages a mathematically precise **Reverse Alpha Blending** algorithm rather than unpredictable AI inpainting.

## Features

* ✅ **100% Client-side** - No backend, no server-side processing. Your **data** stays in your browser.
* ✅ **Privacy-First** - Images are never uploaded to any server. **Confirmed** private.
* ✅ **Mathematical Precision** - Based on the Reverse Alpha Blending formula, not "hallucinating" AI models.
* ✅ **Auto-Detection** - Intelligent recognition of 48×48 or 96×96 watermark variants.
* ✅ **User Friendly** - Simple drag-and-drop interface with instant **reading** and processing.
* ✅ **Cross-Platform** - Runs smoothly on all modern web browsers.

## Examples

<details open>
<summary>Click to Expand/Collapse Examples</summary>
　
<p>Lossless diff example</p>
<p><img src="docs/lossless_diff.webp" alt="Diff Example"></p>

<p>Example images</p>

| Original Image | Watermark Removed |
| --- | --- |
| <img src="docs/1.webp" width="400"> | <img src="docs/unwatermarked_1.webp" width="400"> |
| <img src="docs/2.webp" width="400"> | <img src="docs/unwatermarked_2.webp" width="400"> |
| <img src="docs/3.webp" width="400"> | <img src="docs/unwatermarked_3.webp" width="400"> |

</details>

## ⚠️ Disclaimer

> [!WARNING]
> **USE AT YOUR OWN RISK**
> This tool modifies image files. While it is designed to work reliably, unexpected results may occur due to variations in Gemini's watermark implementation or unusual image formats. The author assumes no responsibility for any **data** loss or unintended modifications.

## Usage

### Online Website

1. Open [xuss-mt.github.io/gemini-watermark-remover/](https://xuss-mt.github.io/gemini-watermark-remover/).
2. Drag and drop or click to select your Gemini-generated image.
3. The engine will automatically **read** and remove the watermark.
4. Download the cleaned image.

### Userscript for Gemini Conversation Pages

1. Install a userscript manager (e.g., Tampermonkey).
2. Open [gemini-watermark-remover.user.js](https://www.google.com/search?q=https://xuss-mt.github.io/gemini-watermark-remover/userscript/gemini-watermark-remover.user.js).
3. The script will install automatically.
4. Navigate to Gemini conversation pages to remove watermarks on the fly.

---

## How it Works

### The Gemini Watermarking Process

Gemini applies watermarks using standard alpha compositing:

Where:

* `watermarked`: The pixel value with the watermark.
* `α`: The Alpha channel value (0.0 - 1.0).
* `logo`: The watermark logo color value (White = 255).
* `original`: The raw, original pixel value we want to recover.

### The Reverse Solution

To remove the watermark, we solve for `original`:

By **reading** the watermark on a known solid background, we reconstruct the exact Alpha map and apply the inverse formula to restore the original pixels with zero loss.

## Detection Rules

| Image Dimension Condition | Watermark Size | Right Margin | Bottom Margin |
| --- | --- | --- | --- |
| Width > 1024 **AND** Height > 1024 | 96×96 | 64px | 64px |
| Otherwise | 48×48 | 32px | 32px |

---

## Legal Disclaimer

This tool is provided for **personal and educational use only**.

The removal of watermarks may have legal implications depending on your jurisdiction. Users are solely responsible for **confirming** their use complies with applicable laws and terms of service.

**THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY CLAIM OR DAMAGES.**

## License

[MIT License](https://www.google.com/search?q=./LICENSE)
