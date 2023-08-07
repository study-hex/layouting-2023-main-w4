# layouting-2023-main-w4

- 主線任務-W4

> <https://rpg.hexschool.com/task/349/show>

- 設計稿

> <https://xd.adobe.com/view/5b20cbc4-5c64-4b67-814e-633b078a8cd4-0e73/grid>

---

## RE-FIX-LV1

- [x] 在 768px 時就先將導覽列變為手機版型，元素彼此才不會太擁擠
  - （導覽列會在 510px 以下時出現 X 軸）

> ![x](https://hackmd.io/_uploads/Skc0XX5s2.png)

- [x] .main 不需要在 768 以下時移除左右邊的 padding，這會讓網頁內容太接近邊緣

---

## LV.2

### SCSS

```markdown
+---base
|       _base.scss      <!-- global tags -->
|       _font.scss
|       _reset.scss
|       
+---components
|       _button.scss
|       _scrollbar.scss
|       
+---layout
|       _footer.scss
|       _header.scss
|       _navbar.scss
|       
+---pages
|       _faq.scss
|       _index.scss
|       _store.scss
|       
+---themes
|       _theme.scss     <!-- color -->
|       
\---utils
        _functions.scss <!-- margin, padding, gap -->
        _helpers.scss   <!-- container, display -->
        _mixins.scss    <!-- media -->
        _variables.scss
```

### p3-首頁

- 表單選項框框客製化

> <https://codepen.io/NoNameNote/pen/qBQgOOb>

---

## LV.1

```markdown
LV1：任選 2 頁含 RWD
```

- [x] p1-門市據點資訊頁
- [x] p2-常見問題頁

### SCSS

```markdown
+---base
|       _base.scss       <!-- container, gap, font -->
|       _reset.scss
|       _variables.scss
|       
+---layout
|       _footer.scss
|       _header.scss
|       
+---pages
|       _faq.scss
|       _index.scss
|       _store.scss
|       
\---utils
        _helpers.scss  <!-- display, flex, z-index -->
        _mixins.scss   <!-- pad, phone -->
```

### p1-門市據點資訊頁

- 下拉選單移除原生按鈕

```CSS
  /* Remove default arrow */
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
```

- 選單移除外框

```CSS
  outline: none;
```

- 地圖匯入的 `iframe` 內建尺寸設定改為適應外層容器

### p2-常見問題頁

- ~~按照設計稿增加內推 `px-55`~~

> 咦？我忘了為什麼，但是這個不需要，改為 `md-w-full`

---

## 原版指令說明

### Node.js 版本

- 專案的 Node.js 版本需為 v16 以上
- 查看自己版本指令：`node -v`

---

### 指令列表

- `npm install` - 初次下載該範例專案後，需要使用 npm install 來安裝套件
- `npm run dev` - 執行開發模式
  - 若沒有自動開啟瀏覽器，可嘗試手動在瀏覽器上輸入
    `http://localhost:5173/<專案名稱>/pages/index.html`
- `npm run build` - 執行編譯模式（不會開啟瀏覽器）
- `npm run deploy` - 自動化部署

---

### 資料夾結構

- assets # 靜態資源放置處
  - images # 圖片放置處
  - scss # SCSS 的樣式放置處
    - layout # ejs 模板放置處
    - pages # 頁面放置處

- JavaScript 程式碼可寫在 main.js 檔案

#### 注意事項

- 已將 pages 資料夾內的 index.html 預設為首頁，建議不要任意修改 index.html 的檔案名稱

- .gitignore 檔案是用來忽略掉不該上傳到 GitHub 的檔案（例如 node_modules），請不要移除 .gitignore

### 開發模式的監聽

vite 專案執行開發模式 `npm run dev` 後即會自動監聽，不需要使用 `Live Sass Compiler` 的 `Watch SCSS` 功能

---

### 部署 gh-pages 流程說明

#### Windows 版本

1. 在 GitHub 建立一個新的 Repository

2. 部署前請務必先將原始碼上傳到 GitHub Repository 也就是初始化 GitHub，因此通常第一步驟會在專案終端機輸入以下指令

```cmd
git init # 若已經初始化過就可以不用輸入
git add .
git commit -m 'first commit'
git branch -M main
git remote add origin [GitHub Repositories Url]
git push -u origin main // 僅限第一次輸入，往後只需要輸入 git push
```

```markdown
3. 初始化完畢後，執行 `npm run deploy` 指令進行自動化部署
```
