# Totoro-web PDF Font

totoro-web 目前使用的字體為 [TW-Sung-98_1-mix.ttf](https://github.com/dentallio/totoro-fonts/blob/master/TW-Sung-98_1-mix.ttf)，使用 CNS11643 中文標準交換碼全字庫(簡稱全字庫) [宋體字型檔](https://data.gov.tw/dataset/5961)，並把生僻字型補進字體

## 補生僻字流程

下載後會有三個字型檔：

- TW-Sung-98_1.ttf：為基本字型集
- TW-Sung-Ext-B-98_1.ttf：增補字型檔（對應至 Unicode 的第 2 字面）
- TW-Sung-Plus-98_1.ttf：增補字型檔（對應至 Unicode 的第 15 字面）

基本上三個字型檔內容不會重複

以「𤥓」字為例：

1. 到 [unicode-explorer](https://unicode-explorer.com/)，找到這個字對應的 unicode

   搜尋後可以找到 `U+24953`

2. 下載 FontForge [下載點](https://fontforge.org/en-US/downloads/mac/)

3. 開啟 `TW-Sung-98_1.ttf`
   ![tw-sung](/doc/images/tw-sung-plus-font-forge.png)

   通常會照 unicode 順序排列：
   ![sortby-unidcode](/doc/images/sortby-unicode.png)

   會發現沒有這個 unicode 的字符
   到 [全字庫標準交換碼](https://www.cns11643.gov.tw/search.jsp?ID=12) 查詢所在字型，字型資訊有寫到 `此字為 CNS11643 第10字面正編碼`，表示此字型會在 `TW-Sung-Ext-B-98_1.ttf` 裡面(2~14)

   開啟 `TW-Sung-Ext-B-98_1.ttf`
   ![tw-sung-ext](/doc/images/tw-sung-ext.png)

   增補字體檔中會有大量的空白字符，可以用`Encoding > compact(hide unused glyphs)`把空白字型過濾掉比較好找  
    照 unicode 順序找到對應字符後，先 copy 生僻字字符  
    ![copy](/doc/images/copy.png)

4. 到要新增的字體新增一個字符區塊，字區會新增在字體的最後，出現一個可被選擇的 `X` 區塊  
   新增字符區塊  
   ![add](/doc/images/add.png)
   ![add-modal](/doc/images/add-modal.png)

   出現一個可被選擇的 `X` 區塊  
    ![after-add](/doc/images/after-add.png)

5. 貼上生僻字，貼上後，會發現字符的內容是`?`  
   ![paste](/doc/images/paste.png)  
   ![after-paste](/doc/images/after-paste.png)

6. 右鍵編輯字符內容，把 unicode 補上  
   ![edit-info](/doc/images/edit-info.png)  
   ![edit](/doc/images/edit.png)

7. 最後匯出文字  
   ![generate-font](/doc/images/generate-font.png)

隨著字符越來越多，可能會遇到這個錯誤訊息顯示字符數量超過，就只能替換現有字符了  
![error](/doc/images/error.png)
