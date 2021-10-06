# Dcard梗圖
###### tags: `dcard` `memes` `adobe`
###### 撰寫時間 : 2021/09/11

## 製作流程
### 素材來源
1. [Reddit/r/memes](https://www.reddit.com/r/memes/)
2. [iFunny](https://ifunny.co/)
3. [Imgur](https://imgur.com/)
4. 個人靈感

### 軟體製作
- 靜態圖

|檔案格式|`*.png`, `*.jpg`|
|:-:|:-:|
|圖片無損放大|Topaz Gigapixel AI|
|點陣圖片編輯|photoshop|
|(少用)向量圖片編輯|illustrator|

- 動態圖

|檔案格式|`*.gif`|
|:-:|:-:|
|影片編輯|after effects|

### 轉檔與壓縮
- 基於`ffmpeg`的軟體

|名稱|介紹|
|:-:|:-:|
|[voukoder](https://www.voukoder.org/)|提供AE/PR/ME更高編碼效率的render插件|
|[File Converter](https://file-converter.org/)|按兩鍵立即轉換圖片格式|

- GIF壓縮

|名稱|介紹|
|:-:|:-:|
|[I love IMG](https://www.iloveimg.com/compress-image/compress-gif)|壓縮GIF的網頁服務|
|[Gif Compressor](https://gifcompressor.com/)|壓縮GIF的網頁服務|
|[Compress or Die](https://compress-or-die.com/gif)|壓縮GIF的網頁服務，可調較多參數|



### Dcard文章
|項目|說明|
|:-:|:-:|
|標題|個人習慣使用【】做初步的文章標題分類，例如有【插畫】、【動圖】等|
|hashtag|只能標記5個，選擇最多人標記與最符合文章內容的，其中必定包含具有個人標誌的標籤[シオシシオ的迷因專區](https://www.dcard.tw/topics/%E3%82%B7%E3%82%AA%E3%82%B7%E3%82%B7%E3%82%AA%E7%9A%84%E8%BF%B7%E5%9B%A0%E5%B0%88%E5%8D%80)方便進行個人文章熱門排序|

## 個人社群成績
### 目標
- [x] 突破100人追蹤並開通創作者俱樂部
- [X] 文章獲得心情突破十萬個

於2021/07/21成功開通創作者俱樂部帳號，目標達成。

### 歷程
|時間|里程碑|
|:-|:-:|
|2021/01/21|第一篇文，跟hololive有關|
|2021/02/03-4/02|分享自己在YT做的hololive迷因，此時重心仍在[個人Youtube頻道](https://hackmd.io/@HsuChiChen/youtube)經營|
|2021/03/14|在梗圖版上的第1篇文|
|2021/04/15-08/08|在梗圖版密集連發文|
|2021/08/09-|因為已經沒梗、相關流程與修圖技術已鑽研完畢、沒時間等原因已無限期停更|

### 成就(2021/9/11統計)
- [Dcard個人公開頁面](https://www.dcard.tw/@chenneil90121)<br>
`117`文章、`152`追蹤、已開通創作者俱樂部
![](https://i.imgur.com/Gzqr3Ts.png)

- 成就<br>
文章被收藏`7267`次、文章獲得心情`108194`個
![](https://i.imgur.com/oCXa1bn.jpg)

- 單篇文章<br>

|項目|數量|
|:-:|-:|
|[文章最高愛心數](https://www.dcard.tw/f/meme/p/236638233)|`6283`|
|愛心3000以上文章數|`8`|
|愛心2000-2999文章數|`13`|
|[自創梗圖文章最高愛心數](https://www.dcard.tw/f/meme/p/236010577)|`4080`|

## 心得
### 學習動機
如[個人Youtube頻道](https://hackmd.io/@HsuChiChen/youtube)一文所述，主要學的是影片剪輯用到的軟體`After Effects`、`Premiere Pro`，以及縮圖製作用`illustrator`，因此剩`Photoshop`這個強大的點陣圖處理軟體還沒熟悉。

### Photoshop操作
主要是看兩位台灣的Youtuber
- [就 的攝影&後製暗房](https://www.youtube.com/channel/UC99744pPNzMlmQ9O3Xy2XIg)
- [papaya Photoshop基礎教學](https://www.youtube.com/watch?v=Ah8-LWR9LeU&list=PL7enJ2-v6SPnQe5bqB0xupPSRpynhzH_E)


我覺得蠻重要的快捷鍵與功能有:
- 拷貝的圖層：Ctrl + J
- 向下合併圖層（Merge Down）：Ctrl + E
- 反轉：Ctrl + Shift + I
- 羽化：Ctrl + Alt + D
- 調整色階：Ctrl + L
- 調整曲線：Ctrl + M
- 放大顯示：Ctrl + +
- 縮小顯示：Ctrl +  -
- **填滿前景色：Alt + Del**
- **填滿背景色：Ctrl + Del**
- 任意變形：Ctrl + T

另外
- **消失點**可以讓文字完美嵌入到畫面
- **混合模式**各項功能可以合成影像
- 網美最愛用的**液化工具**可以瘦身
- 影像中的**Alpha圖層**紀錄透明參數
- 圖層之間的從屬關係，**按Alt可以建立剪裁遮色片**
- 遮色片，我的理解是**當作一個mask** - 黑色區域是0，代表一個pixel乘上一個0的數值而不顯示；而白色為1，代表一個pixel乘以自己還是自己，因此不受影響

這些都是一些較零碎而基本的知識點，當然沒常用還是會忘，因此我的大原則是:
1. 決定好要做什麼
2. 構思實現的方法
3. 試著把這些想法轉換成具體的關鍵字並google搜尋
4. 如果第3點執行不了，就到其他論壇問問題，例如:[【蕾萌紫】Photoshop+Illustrator平面設計教學交流平台](https://www.facebook.com/groups/1707741355928453)
5. 接著大致上就是照著教學做了

這東西隨著用久了、熟能生巧，開始可以去構思要做什麼，並試個不去找教學自己獨立完成，提升對於軟體的掌握度。

### 軟體的使用與了解程式背後運作的原理是兩回事
現在人人幾乎都會P圖，我當初接觸photoshop也是一下子就上手了，當然、無可否認的是要製作出精美、無可挑剔的影像後製需要下不少功夫，但對於日常使用來說，要上手很容易。

我覺得**軟體的使用與了解程式背後運作的原理是兩回事**，比如說我要上個霧玻璃、馬賽克，大部分人會用[高斯模糊](https://zh.wikipedia.org/wiki/%E9%AB%98%E6%96%AF%E6%A8%A1%E7%B3%8A)，但實際上軟體使用者不知道、也不需要知道高斯模糊背後常態分布的數學模型。又好比今天我要旋轉一個影像，不需要知道背後是由旋轉矩陣的數學公式辦到的。

現在是個高度分工的時代，**計算機底層的人會包好一個接口給更上層的人使用**，而上層的不需要知道那接口背後實踐的原理，如同一個function一樣，我只需要會用輸入與預期得到的輸出就好了。而像adobe這種大公司出產的商用軟體在圖形介面上又做很好的使用者體驗，因此用久了就知道哪些功能在哪裡、上手門檻低，adobe軟體基本使用邏輯也都是差不多的。

### 越爭議的文章越能提升文章曝光度
如[【工作】畢業即就業](https://www.dcard.tw/f/meme/p/236414358)底下留言對於**職業高低**有一些爭論；而[【地獄】又到了每年的5月35日](https://www.dcard.tw/f/meme/p/236165863)底下留言開始**吵政治**......因為太多爭論、吵架、沒意義的內容，所以我不常留言，也不太看留言，但觀察到一個現象
> 爭議越高的文章底下留言變很多，進而帶動文章曝光度，讓更多人加入留言，引起更大規模的爭吵。

或許歸咎於Dcard戰校系、吵架風氣，一開始社群理念應該是為了匿名而單純顯示校名、系級，但這也引發了戰校系或是匿名性太高、分不清楚你我的問題，所以我**不太常看Dcard，而是回歸到創作的本身**，對我來說Dcard只是一個我發文的平台，而我也只是選擇性去看留言汲取回饋而已。
