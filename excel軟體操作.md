# excel軟體操作
###### tags: `電腦` `學習` `軟體`
###### 撰寫時間 : 2021/09/12-09/14

## 教學影片
[PAPAYA Excel 基礎教學](https://www.youtube.com/watch?v=wg3R5LdQ56k&list=PL7enJ2-v6SPm-EHMuRMCG7R7C-vXQugNM&index=1)

## 軟體定位
**spreadsheet的處理與日常資料處理**，就算是進階一點的`VBA`感覺用途侷限，不值得學習。要深入，去學`python`、`matlab`、統計系在用的`SAS`、`SPSS`等工具會比較有意義。

## 知識點
- 向下移動`enter`、向右移動`tab`、向左移動`shift+tab`
- 凍結窗格使表格下滑時，首欄能一直顯示
- 資料排序，可分多層級比較與自定義排序方式
- 資料篩選，提供文字模糊比對、色彩篩選等
- 認識excel匯出到**Power BI**進行資料視覺化
- 插入->表格、格式化表格(讓軟體自動偵測或是使用`ctrl`+`shift`選取表格範圍)
- 交叉分析篩選器(視覺化篩選功能)
- 設定格式化的條件(篩選->把特定資料隱藏;設定格式化->標註特定資料)，提供資料橫條、色階、圖示集等
- 工作表設定、合併彙算
- 圖表內建篩選、材質、股票折線走勢圖、雷達圖、組合圖
- **樞紐分析表(pivot table)**，分篩選、欄、列、值區域如積木一般可進行自定義排列、可組成群組、時間表功能視覺化篩選機制、樞紐分析圖、與原數據連動，並更新資料
- 列印分頁設定、 調整縮放比例、每頁都列印標題列、頁首、頁尾、浮水印
- 預設儲存格是相對參照，在**符號前面加上`$`代表絕對參照**(快捷鍵是反白後按`F4`)，例如`A$1`為相對欄和絕對列
- 可以隱藏儲存格或是工作表
- 文字與公式**串接合併用`&`**，例如`"<"&A1`，代表小於A1儲存格的數，也適用於日期
- **儲存格定義名稱、名稱管理員**->替儲存格取別名，方便調用
- **資料剖析**分隔符號、固定寬度來分隔資料
- 快捷鍵`f4`可重複上一個指令
- 拖曳邊框移動資料、ctrl+拖曳邊框複製資料、shift+拖曳邊框插入資料
- 選擇性貼上->轉置(欄列對調)、**加減乘除運算**
- 移除重複項、`ctrl~`顯示公式、新增註解
- 資料->模擬分析->目標搜尋，**計算出英文要考到幾分才及格?**
- `Alt`+`Enter`儲存格內部換行
- excel會自動判別數字格式 分數`0 1/2`,文字(手機號碼)`'0978` ，以下為[自訂數值格式語法](https://www.youtube.com/watch?v=rR2dKiw9mNo&list=PL7enJ2-v6SPm-EHMuRMCG7R7C-vXQugNM&index=21):

|符號|解釋|
|:-:|:-:|
|`#`|數字，沒有意義不顯示|
|`?`|數字，無意義以**空格**形式呈現，可以對齊數據|
|`0`|數字，**強制顯示**指定的位數|
|`@`|代表**文字**|
|`*`|**填充**其後的符號|
|`,`|**千分位**，簡化大數值|
|`_`|**留白**其後符號的**寬度**|
|`AM/PM`|時間格式轉12小時制|
|`y/m/d/h/m/s`|年/月/日/時/分/秒|
|`aaa/aaaa`|周幾/星期幾|

- 自訂格式`正值; 負值; 零值; 文字`，可變更色彩與輸入條件式的語法
![](https://i.imgur.com/Gt3kc8O.png)
- `ctrl`+`;`靜態抓取現在日期；`ctrl`+`shift`+`;`靜態抓取現在時間
- 保護表格編輯權限、不顯示公式，但我實測會被google doc破解，不管用
- 無法解決問題?找出這些資料的共同特性，並用**輔助欄**進行二段式解決
- 按快捷鍵`F9`可更新表中數據
- excel中**每個日期都有對應的數字**，從1900/01/01日為1開始數，而時、分、秒由小數進行儲存
- **甘特圖(Gantt Chart)**顯示專案、進度等**與時間相關**的系統進展
- 將`true/false`轉換為`1/0`
    1. `--(判斷式)`
    2. `(判斷式)*1`
- 帕列托圖(80/20法則)是指在**原因和結果、努力和收穫之間，普遍存在著不平衡的關係**，譬如80%的利潤由20%的顧客帶來，80%的財富集中在20%的人手中
- 擷取網頁上的資料 
    1. 資料->從web->貼上URL
    2. 自己寫程式或網頁爬蟲軟體parsehub
- 3D地圖視覺化行政區域
- excel亂碼處理?資料->從csv匯入->**將編碼格式轉換成`UTF-8`**
- 李克特量表(Likert scale)是一種心理反應量表，常在問卷中使用
- Forms表單->power query資料整理->power pivot建立資料模型->樞紐分析表
- [power query資料整理](https://www.youtube.com/watch?v=c4ZXLLExG_w&list=PL7enJ2-v6SPm-EHMuRMCG7R7C-vXQugNM&index=39)
- 模擬分析
    1. 目標搜尋-不確定公式需要哪些輸入值才能得到該結果
    2. 運算列表-多個公式都使用同一個共同變數
    3. 規劃求解-多變數、多限制條件


## 函式
- 基礎

|函式|功能|
|:-:|:-:|
|`LARGE(array, k)`|第k個大的數|
|`SMALL(array, k)`|第k個小的數|
|`IF(condition, true, false)`|if條件|
|`IFS([condition1, true1, condition2, true2...)`|if巢狀條件，增加程式可讀性。若要指定預設結果，請在最終的 `logical_test`引數輸入`TRUE`|
|`VLOOKUP(關鍵字,儲存格範圍, 最左邊欄的欄從1開始數 ,精準模糊比對)`|例如以零件編號來查看汽車零件的價格，使用False代表精準比對；True為模糊比對，儲存格範圍需**遞增排列**，`VLOOKUP`已被更好用的`XLOOKUP`所取代|
|`IFERROR(value, value_if_error)`|在選項空白時可以加上`IF`來不顯示錯誤訊息，另外也可用**資料驗證提示輸入訊息與錯誤提醒**|
|`COUNT(資料範圍)`|計算數字儲存格數目|
|`COUNTA(資料範圍)`|計算不是空白的儲存格數目|
|`COUNTA(資料範圍, 條件)`|計算符合條件的儲存格數目|
|`COUNTIF(資料範圍1, 條件1, 資料範圍2, 條件2, ...)`|計算符合多條件的儲存格數目|

- 日期

|函式|功能|
|:-:|:-:|
|`MONTH(value)`|回傳月份|
|`SUMIF(加總範圍, 資料範圍1, 條件1, 資料範圍2, 條件2, ...)`|類似`COUNTIF`，差別是多了加總範圍|
|`INDIRECT(ref_text, [a1])`|傳回文字串所指定的參照|
|`TODAY()`|動態取得現在日期|
|`NOW()`|動態取得現在日期、時間，可以按`F9`手動刷新時間|
|`DATEDIF(start_date,end_date,unit)`|參數有`"Y"`, `"M"`, `"D"`,`"YM"`(月差異，日、年都會被忽略)|
|`NETWORKDAYS(start_date, end_date, [holidays])`|忽略自定義工作日計算|
|`NETWORKDAYS.INTL(start_date, end_date, [weekend], [holidays])`|忽略自定義工作日，再加上例行性放假，例如:`[weekend]=1`星期六、星期日|
|`RANK.EQ(number,ref,[order]=0)`|傳回數字在一數列中的排名，會給重複的數字相同的排名並影響後續的排名。而`RANK.AVG`如果有多個數值的排名相同，則會傳回該組數值的平均排名|

- 字串處理

|函式|功能|
|:-:|:-:|
|`LEFT(text, [num_chars])`|傳回字串前幾個字元|
|`RIGHT(text,[num_chars])`|傳回字串後幾個字元|
|`MID(text, start_num, num_chars)`|字串中指定位置開始，傳回特定的字元數|
|`FIND(find_text, within_text, [start_num])`|傳回該尋找字串在第一個字串中的起始位置，從1開始|
|`LEN(text)`|傳回文字字串中的字元數|

- 範例

|      商品     |   品名   | 性別  | 尺寸 |
|:------------:|:--------:|:----:|:----:|
| 羽絨外套-女-M  | 羽絨外套  |  女  |   M  |
|公式|`=LEFT(B3, FIND("-",B3)-1)`|`=MID(B3, FIND("-",B3)+1,1)`|`=RIGHT(B3,LEN(B3)-FIND("-",B3,FIND("-",B3)+1))`|
|說明|find長度再left擷取|find尋找開始位置，再mid擷取|總長度len減去find找到第二個`"-"`，再right擷取|

- 進階

|函式|功能|
|:-:|:-:|
|`INDEX(array, row_num, [column_num])`|陣列中由列和欄號索引選取的元素值|
|`XMATCH (lookup_value、lookup_array、[match_mode]、[search_mode])`|搜尋單欄、單列中的指定位置|
|`RANDBETWEEN(bottom, top)`|取亂數，可以配合`INDEX`去挑選任意表格|
|`CHOOSE(index_num, value1, [value2], ...)`|根據index回傳一個後面的選項|
|`RAND()`|傳回大於或等於 0 且小於 1 的平均分配隨機實數|
|`ROUNDUP(number, num_digits)`|無條件進位到某一指定位數，同樣也有`ROUND`,`ROUNDDOWN`,`MROUND`(四捨五入到所需倍數的數值)|
|`AND`, `OR`, `NOT`|布林邏輯，但要注意excel中不等於符號為`<>`|
|`=SUMPRODUCT (array1， [array2]...) `|陣列相乘總和|

- 動態陣列

一行公式回傳多筆資料，具有`spilling`的特性。函數範圍在結尾加上`#`能參照到所有`spilling`的欄位。
|函式|功能|
|:-:|:-:|
|`UNIQUE(array)`|傳回範圍中唯一值清單|
|`FILTER(array, condition,[if_empty])`|篩選資料範圍，利用布林運算`(condition1)*(condition2)`代表同時符合兩個狀況的資料才會被篩選到|
|`SORT(array, [sort_index], [sort_order], [by_col])`|排序順序的數字:1表示遞增排序(預設)；-1表示遞減排序|
|`OFFSET(reference, rows, cols, [height], [width])`|傳回根據所指定列數及欄數之儲存格或儲存格範圍之範圍的參照，配合`COUNTA`,`MATCH`可隨輸入不同，動態改變選取範圍|

- 進階2

|函式|功能|
|:-:|:-:|
|`XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found], [match_mode], [search_mode])`|0完全相符;-1下一個較小;1下一個較大;2萬用字元比對(`*`, `？`, `~`)。<br>1預設正向搜尋；-1反向搜尋。|
|`LET(name1, name_value1, calculation_or_name2,...`|新增變數|
|`CONCAT(text1, [text2],…)`|將兩個或多個文字字串合併成一個字串，等同於`&`，但可一次選取範圍|
|`CHAR(number)`|CHAR(65)='A' CHAR(10)=(換行)|
|`PMT(rate, nper, pv, [fv], [type])`|利率、期數、本金|
|`=LAMBDA([parameter1, parameter2, ...],計算)`|於公式->定義名稱**建立subfunction**|