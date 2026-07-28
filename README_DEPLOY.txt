DiamondMind 創辦人後台 V18.17.3
==============================

建議儲存庫
----------
diamondmind-founder

預計網址
--------
https://gigia1127520-gif.github.io/diamondmind-founder/

功能
----
- 營運總覽
- 每日免費精選發布
- Pro 獨贏／讓分／大小分發布
- 串關發布
- 推薦紀錄
- 自動／人工結算監控
- 會員與交易管理
- 公告管理
- 模型績效
- 系統狀態
- 會員臨時密碼重置與強制改密碼
- NPB／KBO／CPBL 真實盤口主備援狀態
- 區分 API 額度用盡、來源異常與盤口尚未提供
- 顯示盤口來源、最後抓取時間與永久快照鮮度
- 開賽前 12 小時內取得首筆真實盤口即可自動發布亞洲棒球

串接方式
--------
- 與會員網站共用 https://diamondmind-api.onrender.com
- 與會員網站共用同一個 Supabase 專案
- 後台按正式發布後，會員端會從同一份正式發布資料讀取並顯示
- 會員端與創辦人後台都有推薦紀錄頁
- 後端所有管理 API 仍會驗證 Supabase role=admin/founder，不能只靠前端隱藏

首次部署
--------
1. 建立新的公開 GitHub 儲存庫：diamondmind-founder。
2. 將 index.html、404.html、manifest.webmanifest 上傳到根目錄。
3. Settings → Pages → Deploy from a branch → main / root。
4. 到 Supabase：
   Authentication → URL Configuration → Redirect URLs
   加入：
   https://gigia1127520-gif.github.io/diamondmind-founder/
5. 使用創辦人帳號登入驗證。

後端
----
使用 DiamondMind Backend V22.4.3；須先在 Supabase SQL Editor 執行
DIAMONDMIND_V22.4.3_SUPABASE_盤口快照.sql.txt，讓最後真實盤口與
免費 API 冷卻狀態可跨 Render 重啟保留。無需新增 Render 環境變數；
既有 ODDS_API_IO_KEY 會同時供 MLB、NPB、KBO、CPBL 使用。
兩個 GitHub Pages 儲存庫都位於同一個 github.io origin，
現有後端 CORS 設定已允許該 origin。
