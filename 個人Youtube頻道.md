# 個人Youtube頻道
###### tags:`adobe` `youtube`
###### 撰寫時間 : 2021/09/16

## 個人logo
以個人姓名為主體，因為我也想不到什麼能代表個人特色與有識別性的icon。

### 靜態圖
![](https://i.imgur.com/IIq1vRQ.png)
發想是Adobe Photoshop這個軟體的logo，PS圓滑文字`#001E36`配上底色`#001E36`，簡單明瞭，又顯得典雅；而外層光暈是參考Apple M1晶片的視覺圖。因此字體選擇`jf open 粉圓 1.1`以呈現圓滑感，選擇漸變工具從`2A90FF`、`9868FF`到`FF43FF`、從左上拉到右下、對比度從小到大。而下面的光暈先拉個圓，漸層效果與文字保持一致，再加上總量為35的【放射性模糊】拉到最後一個圖層，呈現日蝕的效果。


### 動態圖(GIF)
![](https://i.imgur.com/FoesITU.gif)
先弄背景，選【gradient ramp】，漸層由上往下拉，全黑到深藍。接下來字體選`jf open 粉圓 1.1`，呈現圓滑的感覺。再用矩型工具加上一個同背景寬度的矩型，選擇裡面`fill`->`color`打上3個關鍵幀，顏色`1EA6FF`->`631AF2`在回來，以呈現GIF循環撥放的infinite loop。

把漸層變換的矩型拉到文字下面，選擇alpha蒙板`TrkMat`->`Alpha Matte "文字"`。讓**文字呈現變形**的效果，`animate`->`skew`，打關鍵幀從0度到360度，以呈現GIF循環撥放的infinite loop。最後讓文字有光暈的效果，這部分在`AI`需要多層**高斯模糊**疊圖，而`AE`較方便，選擇【glow】即可。


## 影片縮圖
對於`Illustrator`的啟蒙與認識，相關縮圖也經歷過好幾次的重新繪製、練習，覺得自己比較成功的有以下幾個 :

### 高中國防課作品
![](https://i.imgur.com/zFzdSoC.jpg)
參考教學影片[Illustrator wavy flag tutorial](https://www.youtube.com/watch?v=yyhmGsZRpxc)，呈現國旗飄逸的立體感，也弄一個代表軍方的迷彩材質的文字(文字圖層的mask)，並嵌在飄逸的國旗上。

### 大二計算機組織期末專題demo
![](https://i.imgur.com/ak0sXx9.jpg)
字體`MS UI Gothic標準`，選擇內建【書法一】線條圖筆刷，框上白邊線，背景放實驗成品，在加上透明度70%與色碼`B4E9FF`的淺藍色矩形當作是背景圖片的濾鏡。

### 雷射光學實驗
![](https://i.imgur.com/Se6An2N.jpg)
為了視覺化實驗用到的紅外線給一般人的感受，先將背景圖調暗，以凸顯出標題，字體使用**高斯模糊**，而上方標題則另外疊了外層高斯模糊的字體，呈現neon light的效果。


## 學校demo
拿過去粗剪輯的影片當素材練習，以第一個練習為主 :

### [大二計算機組織期末專題demo](https://www.youtube.com/watch?v=LY89O8TjXG8&t=18s)
第一部影片的製作，從**大二寒假開始**真正學習，主要用到`AE`, `PR`, `AI`和少部分的`PS`, `AU`，主要學到有:
- `AE`, `PR`, `AI`基本介面邏輯與操作
- Adobe家族之間的`dynamic link` (強大相容性，超好用)
- AE的Motion Tracking
- [使用現成PR字體模板](https://www.youtube.com/watch?v=U8Bbj6zjJT8)
- AE的callout title製作(搭配Motion Tracking +拉mask彈出字幕)
- AE的3D-camera
- AI的流程圖繪製
- 字體隨時間變色
- 時間軸隨時間變化
- 利用AU把背景音樂自動remix到符合影片長度

反省:
- 由於是4K剪輯，應該要設`proxy`(代理檔案)加速預覽速度
- render應該使用`voukoder`這個plug-in提高影片編碼效率
- **很多動畫與場景是非必要的**，為嘗試而嘗試，應該以簡單、清楚、明瞭為大原則

### [大一普通物理實驗](https://www.youtube.com/watch?v=ok2eS2Bckzg)
看了教學影片[破解YouTuber的綜藝字卡](https://www.youtube.com/watch?v=FwcDLta7UH8)後，開始練習PR的舊版標題，但整體還說畫質沒有很好、伸縮時線條寬度沒有保持一致，成品有點失敗。


## hololive迷因
### [當囂張兔出現在Pui Pui天竺鼠車車](https://www.youtube.com/watch?v=hRRbe_9-Jlc)
2021冬番【天竺鼠車車】這部動畫在台、日流行，播到第05話時，看到蘿蔔與戲劇性的發展讓我想到[標準結局的囂張兔](https://www.youtube.com/watch?v=bwIMzi191Rg)這個影片，因此就兩相結合，pekora本身的聲音也很搞笑，這部是觀看破1000，也是我覺得最成功的一部。

### [害統神端火鍋跌倒的人是哈洽馬!?](https://www.youtube.com/watch?v=Z9rccHEhwsQ)
跟風統神端火鍋的流行，用哈洽馬洗腦的**哈洽馬**口頭禪多音軌疊加，而在細節部分，我有另外拉遮罩，使一個哈洽馬的頭不會蓋住統神的頭，而跌倒時火鍋下墜連同那個哈洽馬的頭，哈洽馬的頭套上動態模糊，符合視覺上看到物體運動的真實感。

### [神奇寶貝 猜猜我是誰](https://www.youtube.com/watch?v=sq-v9ZLU9Xc)
練習使用AE的`Roto Brush`進行影片去背，看到露西亞的新短片[るんるんる…？](https://www.youtube.com/watch?v=TyPV065xWM0)，那時hololive流行玩這部2015獨立遊戲大作【undertale】，我自己也是有破到二周目的和平線，把露西亞結合undertale的chara([屠殺線介紹](https://www.youtube.com/watch?v=ztHpE6oA7AI))，從一開始神奇寶貝猜猜我是誰到結尾就變成恐怖的屠殺線，其中把神奇寶貝的logo給染紅，我非常喜歡這部分的效果。

## 上字幕
參考以下教學 :
- [每次替影片上字幕都覺得很厭世？學會這招讓你從谷底反彈重生！](https://www.youtube.com/watch?v=Fz9VRqSFZAc)
- [Arctime制作双语字幕流程详解](https://www.youtube.com/watch?v=02h6e9QsUJQ)

我認為**語音辨識自動生成字幕軟體**目前效果沒有很好，所以還是建議錄音之前先擬定好草稿，照稿演出。另一個**ARCTIME上字幕軟體**可加速工作的速度 - 打好`*.txt`文字檔再匯入軟體，利用快捷鍵`J`、`K`標記時間軸，之後進行局部微調，最後匯入字幕分為 :
- 內嵌`xml`+`png sequence`到PR
- 外嵌`srt`字幕檔到youtube

主要學習上字幕到[大二計算機組織期末專題demo](https://www.youtube.com/watch?v=LY89O8TjXG8&t=18s)與以下hololive成員翻唱影片:
- [Gawr Gura - Shiny Smily Story](https://www.youtube.com/watch?v=HIIiO-56qDk)
- [潤羽るしあ - ANIMA](https://www.youtube.com/watch?v=xYOcOiugMAg)
- [湊あくあ - あくあ色ぱれっと](https://www.youtube.com/watch?v=l1ZrmhpUFVI)

## Youtube上架
看了很多[Greyson Zhang](https://www.youtube.com/c/GreysonZhang/featured)的頻道教學與一些文章要注意的事情還不少，有以下幾點:
|項目|說明|
|:-:|:-:|
|標題|取聳動又不失影片主題、多用關鍵字，我另外以`【】`做為個人影片分類|
|說明欄|標記影片時間軸標記(要從`00:00`開始)、關鍵字、hashtag等內容打好打滿，格式與編排參考[PAPAYA電腦教室](https://www.youtube.com/channel/UCdEpz2A4DzV__4C1x2quKLw)|
|縮圖|縮圖製作是觀眾要點不點這部影片的判斷依據，相關作品如前述[影片縮圖](#影片縮圖)|
|標記|標記所有可能出現的關鍵字|
|CC字幕|內嵌字幕外，再外嵌CC字幕並完美覆蓋原字幕，方便演算法搜尋|
|資訊卡|讓看完影片的人能看其他自己推薦的影片|
|首頁|自定義編輯首頁，主打影片、精選版面的影片撥放清單|
|簡介|logo與banner設計、簡介、外部連結|

## 心得
### 學習動機
一直很喜歡看Youtube，對影片剪輯有強烈的興趣，很好奇別人影片那些酷炫的效果是怎麼弄的，尤其是以下text reveal效果與motion tracking效果。
![](https://i.imgur.com/Jb7n9iR.gif)

### adobe軟體操作
看了Youtube很多免費教學影片，自己照著實踐並熟悉各種快捷鍵，主要學習特效軟體`After Effects`、剪輯軟體`Premiere Pro`，以及向量圖編輯軟體`illustrator`，也了解[影像編碼的基本知識](https://www.youtube.com/watch?v=d_24Tgsc0vo)。