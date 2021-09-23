# 如何使用Modelsim進行數位電路模擬
###### tags:`modelsim` `verilog`
###### 撰寫時間 : 2021/08/24

## 前言
僅為測試小電路區塊方便用，Windows環境`makefile`、`shell script`、`unix-like`指令、`macro`展開都沒辦法用或是比較麻煩。實際還是要用學校工作站`linux`環境下`NC Verilog`、`Verdi`、`design vision`等一系列EDA tools進行模擬、合成。

## 步驟
1. 用文字編輯器(`vim`, `vscode`)寫好整個電路架構與要用測試的testbench`*.v`(與golden data`*.dat`)，放在同一目錄。
![](https://i.imgur.com/NuPHDmw.png)

2. 打開Windows 10下的`Modelsim v10.1c`

3. `file`->`change Directory`->選擇工作目錄，等同於指令`cd`到工作目錄，於下方`Transcript`視窗也可觀察到是一樣的，差別只是一個用`GUI`，一個用`CLI`而已。
![](https://i.imgur.com/bDW24TZ.gif)

4. 創建`work`目錄，此目錄將存放`Modelsim`模擬時產生的部分檔案。
```
vlib work
```

5. 編譯所有`*.v`檔
```
vlog *.v
```
![](https://i.imgur.com/nFihban.gif)

6. 選擇`work`目錄下的`testbench`並**按右鍵**，選擇`Simulate Without Optimatization`
![](https://i.imgur.com/p52lpb3.gif)

7. 將想要觀察的波型`drag and drop`到`wave`面板
![](https://i.imgur.com/uOBAdHC.gif)

- 如果沒有`wave`面板或不小心關閉，到上方工具列`view`->`New Window`->`Wave`開啟。

8. 跑一個比`testbench`中開始到`$finish`更久時間的秒數
```
run 10000000000ns
```
9. 在執行到`$finish`後，`Modelsim`會跳出視窗詢問是否結束，選擇結束會如同`$finish`一樣關閉程式，因此選擇`No`，以便後續觀察波形。
![](https://i.imgur.com/9m4Bdug.gif)

10. 按快捷鍵`F`可全畫面的波型顯示，而對任意波型**按右鍵**->`Radix`可以改變進位制。
![](https://i.imgur.com/LYAQ2t5.png)

11. 剛才的`Transcript`視窗產生的所有文字可於目錄`C:\modeltech64_10.1c\examples`找到，程式每執行一次就會自動覆蓋掉前一個`Transcript`檔案。
![](https://i.imgur.com/I66ruuz.png)

12. 最終產生預期的灰階圖、work資料夾與`*.wlf`，`*.wlf`為波型檔，下次可以直接打開`Modelsim`->`file`->`open`->選擇該檔案，就可看到之前產生的波型圖。
![](https://i.imgur.com/TOAiX2K.png)

> 僅列舉一小部分自己常用的，更多指令與功能，請見Mentor Graphics官方PDF文檔。
- [ModelSim® User’s Manual Software Version 10.1c](https://www.microsemi.com/document-portal/doc_view/131619-modelsim-user) 

