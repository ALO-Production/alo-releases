# ALO Releases

[ALO Production](https://www.aloproduction.tw/) 旗下產品的公開發佈與版本資訊索引。

## 產品

- **Scena** — DaVinci Resolve 字幕校正 + 字卡編輯套件
- **Foley** — DaVinci Resolve × Eagle 媒體瀏覽工具

## 檔案說明

- `version.json` — 各產品的最新版本資訊。Scena / Foley 啟動時會自動讀取此檔以提示使用者是否有新版本。
- GitHub Releases — 各版本的打包安裝檔（macOS `.dmg` / Windows `.exe`）。

## version.json schema

```json
{
  "<product_key>": {
    "latest": "vX.Y.Z",
    "download_url": "https://...",
    "release_notes": "https://...",
    "min_supported": "vX.Y.Z"
  }
}
```

- `latest`：最新穩定版版本號
- `download_url`：使用者按「前往下載」會開啟的網址
- `release_notes`：更新內容說明頁
- `min_supported`：預留欄位；未來若有強制升級需求時啟用

## 給開發者

更新版本時：

1. 在源碼 repo（私有）完成版本工作並打 git tag
2. 打包產生 `.dmg` / `.exe`
3. 在本 repo 建立對應的 GitHub Release，上傳安裝檔
4. 更新 `version.json` 的 `latest` 與 `release_notes` 連結，commit & push

使用者下次啟動 Scena / Foley 時會自動收到提示。
