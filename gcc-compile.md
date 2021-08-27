# GCC與編譯過程

[![hackmd-github-sync-badge](https://hackmd.io/WqlivhrUT3eFH_HNLX-YYA/badge)](https://hackmd.io/WqlivhrUT3eFH_HNLX-YYA)

###### tags: `linux` `gcc編譯` `C` `C++`
###### 最後更新時間 : 2021/08/17

## 流程圖
![Flowchart](https://i.imgur.com/x0eUstJ.png)

## 編譯過程
### 編輯器 (Editor)
檔名: `.c`
- vim
- vscode

### 預處理器(Preprocessor)
檔名: `.c` -> `.i` <br>
將包含標頭檔文件插入原文件中、將macro展開展開、根據條件編譯命令選擇要使用的代碼
- header files[`#include`](https://zh.wikipedia.org/wiki/%E5%A4%B4%E6%96%87%E4%BB%B6)
- macro 展開[`#define`](https://openhome.cc/Gossip/CGossip/Macro.html)
- 條件編譯命令`#if`,`#ifdef`

### 編譯器(Compiler)
檔名: `.i` -> `.s` <br>
包含詞法分析 (Lexical analysis)、語法分析 (Parsing、Syntax analysis)、語意分析 (Semantic analysis)、符號表 (Symbol Table)、中間碼產生 (Intermediate Code Generation)、最佳化 (Code Optimization)、目標語言產生 (Code Generation) 

- 組合語言 (Assembly)
會針對不同電腦架構(`x86-64`、`ARM`、`MIPS`)及作業系統(`linux`, `MacOS`,`Linux`)而有不同，會需要這樣是因為對於不同的架構可以有不同的優化方式，並且可以使高階語言有可攜性，代表高階語言不需要為了不同的環境寫不同的程式碼，而是透過編譯器將程式碼轉成對應環境的組合語言

### 組譯器 (Assembler)
檔名: `.s` -> `.o` (obj文件) <br>
將低階語言所寫的程式翻譯成目的檔

- 目的碼(Object codes)
CPU 可以直接執行的機器碼 (Machine code) 或是暫存器傳遞語言 (Register transfer language、RTL)，GCC 為後者
目的檔可以透過連結成為可執行檔或是函式庫 (Library)

### 連結器 (Linker)
檔名: `.o` -> `執行檔`(default `a.out`) <br>
將多個目標檔或靜態函式庫 (Static library) 合併成一個可執行檔或函式庫的工具

![](https://i.imgur.com/cThGlaL.png)

### 載入器 (Loader)
是作業系統的一部份，用於把程式和動態函式庫 (Shared library) 的指令載入到記憶體 (RAM) 中等待 CPU 執行，當載入完成之後，作業系統會將控制權交給載入的程式碼，讓它開始運作

### CPU (Central Processing Unit)
對載入的指令進行運算或儲存等操作


## gcc編譯過程
1. 預處理 
> (不生成文件，需要把它重定向到一個輸出文件裡面)
```
gcc -E hello.c > pianoapan.txt
```

2. 預處理、編譯  
>`.c` -> `.s`
```
gcc -S hello.c
```

3. 預處理、編譯、組譯
> `.c` -> `.o`
```
gcc -c hello.c
```
4. 預處理、編譯、組譯、連結 
> `.c` -> `執行檔`(default `a.out`)
```
gcc  hello.c
```

5. 載入器、CPU 執行檔
> (default `a.out`) -> 執行結果
```
./a.out
```

## gcc其他參數


## Tips
- 如果文件非常多的時候，只是修改了一個文件，所有文件都會被重新編譯一次，編譯的時候就會需要很長時間。
- 對於這些源文件，我們應該寫`Makefile`分別處理，執行：預處理 編譯 匯編 ，先分別編譯它們，最後再把它們連接

## 介紹文章與參考資料
- [GCC和Makefile编译过程](https://blog.csdn.net/sinat_31039061/article/details/98885275)
- [C 語言編譯到執行流程](https://aben20807.blogspot.com/2018/08/1070824-c.html)
- [GCC 編譯器基本使用教學與範例](https://blog.gtwang.org/programming/gcc-comipler-basic-tutorial-examples/)
- [Makefile的写法影片](https://www.youtube.com/watch?v=E1_uuFWibuM)
- [Debugging - GDB Tutorial Clip](https://www.youtube.com/watch?v=bWH-nL7v5F4)
- [官方文檔](https://gcc.gnu.org/onlinedocs/gcc/Invoking-GCC.html)
- [相關參數整理](https://gist.github.com/idhowardgj94/9a3a523e66f04ca87c3c41fa691128c5#:~:text=GCC%20%E6%98%AFGNU%20%E7%9A%84C,%E4%B8%A6%E7%94%9F%E6%88%90%E5%8F%AF%E5%9F%B7%E8%A1%8C%E6%96%87%E4%BB%B6%E3%80%82)
