# 投資研究儀表板（教學版）

這是一個可直接部署到 GitHub Pages 的單頁網頁工具，提供：

- 公司/代碼查詢（預設支援「聯發科 -> 2454.TW」映射）
- 價格圖與技術分析（SMA20/SMA50、RSI、MACD）
- 通膨、利率、風險溢酬等宏觀假設可調
- 估值區間計算（便宜價 / 合理價 / 昂貴價）
- 長期資金配置建議（依風險承受度、投資期限）

> ⚠️ 本專案僅供教育與研究用途，不構成投資建議，亦不保證報酬。

## 本機啟動

直接開啟 `index.html` 即可，或用任一靜態伺服器：

```bash
python3 -m http.server 8080
```

## 上傳到 GitHub

1. 建立新 repo（例如 `invest-dashboard`）
2. 推送程式碼：

```bash
git init
git add .
git commit -m "feat: add investment research dashboard"
git branch -M main
git remote add origin <your-repo-url>
git push -u origin main
```

3. 到 GitHub `Settings -> Pages`
4. Source 選擇 `Deploy from a branch`
5. Branch 選 `main` + `/root`
6. 儲存後等待部署完成

## 使用方式（以聯發科為例）

1. 在查詢欄輸入 `聯發科` 或 `2454.TW`
2. 按「載入價格資料」
3. 依你的總經條件調整通膨、利率等
4. 依財報與產業判斷輸入 EPS / 成長率 / 折現率 / 目標本益比
5. 讀取估值區間與技術訊號，搭配風險配置產生策略

## 核心限制

- 自動價格抓取依賴公開資料來源，可能遇到來源封鎖或延遲。
- 估值模型採簡化版（5 年成長 + 終值折現），需搭配現金流與情境分析。
- 技術分析僅反映歷史統計特徵，不代表未來必然走勢。
