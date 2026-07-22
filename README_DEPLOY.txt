DiamondMind 創辦人後台 V18.14.5
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
使用無 EV 的 V21.0.0；不需要為網站分離新增 SQL。
兩個 GitHub Pages 儲存庫都位於同一個 github.io origin，
現有後端 CORS 設定已允許該 origin。
