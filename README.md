# 小新的投資筆記

「小新的投資筆記」漫畫網站——首頁是集數列表，點進去是單集閱讀頁，可以往前後翻集數。純靜態網站，沒有後端，直接放到 GitHub Pages 就能上線。

## 檔案結構

```
index.html          網站本體（版面、樣式、集數資料都寫在這一個檔案裡）
images/              每集的漫畫圖檔（ep01.webp ~ ep10.webp；ep06 有 4 張，因為原圖是分開上傳的）
images/thumbs/       首頁列表用的縮圖
```

## 新增集數

1. 把新一集的圖檔放進 `images/` 資料夾（建議轉成 `.webp` 壓縮過的圖，檔案比較小，網站開起來比較快）。
2. 打開 `index.html`，搜尋 `EPISODES`，會看到一個陣列，每一集是一個物件，例如：

```js
{ id:'ep11', num:11, title:'新的一集標題', teaser:'放這一集最有記憶點的一句台詞', images:['images/ep11.webp'] }
```

- `id`：這一集的網址代號，建議照順序取名，例如 `ep11`
- `num`：集數數字
- `title`：集數標題
- `teaser`：首頁列表會顯示的一句話（目前都是用漫畫裡實際的台詞）
- `images`：這一集的圖檔路徑，一張或多張都可以（多張就是像 ep06 那樣依序排列）

把這個物件加到陣列最後面，存檔就完成了，不需要改其他地方。

## 放到 GitHub Pages

1. 到 GitHub 建一個新 repository（例如 `xiaoxin-investment-notes`）。
2. 把這個資料夾裡的所有檔案上傳（或用 git push）到這個 repo 的 `main` 分支。
3. 到 repo 的 **Settings → Pages**，Source 選 `Deploy from a branch`，Branch 選 `main` / `root`，儲存。
4. 等 1-2 分鐘，就可以用 `https://<你的帳號>.github.io/<repo名稱>/` 打開網站。

## 之後想擴充功能

目前是最簡單的純靜態網頁（一個 HTML 檔 + 圖片），之後如果想加角色介紹頁、課程大綱、留言、後台上傳等功能，可以再回來找我，我可以幫忙規劃怎麼調整這個專案的架構。
