# GCC指令參數
###### tags: `code` `C` `gcc`
###### 撰寫時間 : 2021/09/11

已刪除的網路文章重新編排。

## 介紹
`gcc`,`g++`分別是`gnu`的`c`,`c++`編譯器，`gcc/g++`在執行編譯工作的時候，總共需要4步
1. **預處理器cpp**<br>
預處理，生成`.i`的文件
2. **編譯器egcs**<br>
將預處理後的文件不轉換成彙編語言,生成文件`.s`
3. **彙編器as**<br>
有彙編變為目標代碼(機器代碼)生成`.o`的文件
4. **鏈接器ld**<br>
連接目標代碼，生成可執行程序

## 參數詳解
### -x language filename
- 說明<br>
**設定文件所使用的語言，使後綴名無效**，對以後的多個有效，也就是根據約定C語言的後綴名稱是`.c`的，而`C++`的後綴名是`.C`或者`.cpp`，如果你很個性，決定你的`C`代碼文件的後綴名是`.pig`，那你就要用這個參數，這個參數對他後面的文件名都起作用，除非到了下一個參數的使用<br><br>
可以使用的參數有下面`c`, `objective-c`, `c-header`, `c++`, `cpp-output`, `assembler`, and `assembler-with-cpp`
- 範例
```　　
gcc -x c hello.pig
```

---
### -x none filename
- 說明<br>
**關掉上一個選項**，也就是讓`gcc`根據文件名後綴，自動識別文件類型
- 範例
```
gcc -x c hello.pig -x none hello2.c　
```

---
### -c
- 說明<br>
只激活預處理、編譯和彙編也就是他只把程序做成`.obj`文件
- 範例
```
gcc -c hello.c
```
他將生成`.o`的`obj`文件

---
### -S
- 說明<br>
只激活預處理和編譯，就是指把文件編譯成為彙編代碼
- 範例
```
gcc -S hello.c
```
他將生成`.s`的彙編代碼，你可以用文本編輯器察看

---
### -E
- 說明<br>
只激活預處理，這個不生成文件，你需要把它重定向到一個輸出文件裡面。
- 範例
```
gcc -E hello.c >; pianoapan.txt
gcc -E hello.c | more
```
一個hello word也要預處理成800行的代碼

---
### -o
- 說明<br>
制定目標名稱，缺省的時候，`gcc`編譯出來的文件是`a.out`
- 範例
```
gcc -o hello.asm -S hello.c
```

---
### -pipe
- 說明<br>
使用管道代替編譯中臨時文件，在使用非`gnu`彙編工具的時候，可能有些問題
- 範例
```
gcc -pipe -o hello.exe hello.c
```

---
### -ansi
關閉`gnu c`中與`ansi c`不兼容的特性，激活`ansi c`的專有特性，包括禁止一些`asm`, `inline`, `typeof`關鍵字，以及`UNIX`、`vax`等預處理宏

### -fno-asm
此選項實現`ansi`選項的功能的一部分，它禁止將`asm`,`inline`和`typeof`用作關鍵字

### -fno-strict-prototype
只對`g++`起作用，使用這個選項，`g++`將對不帶參數的函數,都認為是沒有顯式的對參數的個數和類型說明，而不是沒有參數。
而gcc無論是否使用這個參數，都將對沒有帶參數的函數，認為沒有顯式說明的類型
　　
### -fthis-is-varialble
就是向傳統`c++`看齊,可以使用`this`當一般變量使用.
　　
### -fcond-mismatch
允許條件表達式的第二和第三參數類型不匹配,表達式的值將為`void`類型

### -funsigned-char
### -fno-signed-char
### -fsigned-char
### -fno-unsigned-char
這四個參數是對`char`類型進行設置，決定將`char`類型設置成unsigned char(前兩個參數)或者signed char(後兩個參數)
　　
### -include file
- 說明<br>
包含某個代碼，簡單來說，就是便以某個文件，需要另一個文件的時候，就可以用它設定，功能就相當於在代碼中使用
```
#include<filename>;
```
- 範例
```
gcc hello.c -include /root/pianopan.h
```

### -imacros file
將`file`文件的宏，擴展到`gcc/g++`的輸入文件，宏定義本身並不出現在輸入文件中
　　
### -Dmacro
相當於C語言中的`#define macro`
　　
### -Dmacro=defn
相當於C語言中的`#define macro=defn`
　　
### -Umacro
相當於C語言中的`#undef macro`

### -undef
取消對任何非標準宏的定義
　　
### -Idir
在你是用`#include"file"`的時候，`gcc/g++`會先在當前目錄查找你所制定的頭文件，如果沒有找到，他回到缺省的頭文件目錄找，如果使用`-I`制定了目錄，他會先在你所制定的目錄查找，然後再按常規的順序去找。
對於`#include<file>`，`gcc/g++`會到`-I`制定的目錄查找，查找不到，然後將到系統的缺省的頭文件目錄查找
　　
### -I-
就是取消前一個參數的功能，所以一般在`-Idir`之後使用

### -idirafter dir
在`-I`的目錄裡面查找失敗，講到這個目錄裡面查找


### -iprefix prefix
### -iwithprefix dir
一般一起使用，當`-I`的目錄查找失敗，會到`prefix+dir`下查找

### -nostdinc
使編譯器不再系統缺省的頭文件目錄裡面找頭文件，一般和`-I`聯合使用，明確限定頭文件的位置
　　
### -nostdin C++
規定不在`g++`指定的標準路經中搜索,但仍在其他路徑中搜索，此選項在創`libg++`庫使用
　　
### -C
在預處理的時候，不刪除註釋信息，一般和`-E`使用，有時候分析程序，用這個很方便的
　　
### -M
生成文件關聯的信息。包含目標文件所依賴的所有源代碼你可以用`gcc -M hello.c`來測試一下

### -MM
和上面的那個一樣，但是它將忽略由`#include<file>`，造成的依賴關係
　　
### -MD
和`-M`相同，但是輸出將導入到`.d`的文件裡面
　　
### -MMD
和`-MM`相同，但是輸出將導入到`.d`的文件裡面
　　
### -Wa,option
此選項傳遞option給彙編程序，如果option中間有逗號，就將option分成多個選項，然後傳遞給會彙編程序
　　
### -Wl.option
此選項傳遞option給連接程序，如果option中間有逗號，就將option分成多個選項，然後傳遞給會連接程序

### -llibrary
- 說明
制定編譯的時候使用的庫
- 範例
```
gcc -lcurses hello.c
```
使用`ncurses`庫編譯程序
　　
### -Ldir
這個`dir`就是目錄的名稱。制定編譯的時候，搜索庫的路徑。比如你自己的庫，可以用它制定目錄，不然編譯器將只在標準庫的目錄找

### -O0
### -O1
### -O2
### -O3
編譯器的優化選項的4個級別，`-O0`表示沒有優化，`-O1`為缺省值，`-O3`優化級別最高
### -g
只是編譯器，在編譯的時候，產生調試信息
　　
### -gstabs
此選項以`stabs`格式聲稱調試信息，但是不包括gdb調試信息
　　
### -gstabs+
此選項以stabs格式聲稱調試信息，並且包含僅供gdb使用的額外調試信息.
　　
### -ggdb
此選項將盡可能的生成gdb的可以使用的調試信息

### -static
此選項將禁止使用動態庫，所以編譯出來的東西一般都很大，也不需要什麼動態連接庫，就可以運行

### -share
此選項將盡量使用動態庫，所以生成文件比較小，但是需要系統由動態庫

### -traditional
試圖讓編譯器支持傳統的C語言特性

### -w
不生成任何警告信息

### -Wall 
生成所有警告信息


## 多檔案編譯範例
如果你有兩個或少數幾個`C`源文件，也可以方便地利用`GCC`編譯、連接並生成可執行文件。例如有兩個源文件`main.c`和`factorial.c`兩個源文件，要編譯生成一個計算階乘的程序

- 檔案1名稱`factorial.c`
```c
int factorial (int n)
{
　　if (n <= 1)
　　　return 1;
　　else
　　　return factorial (n - 1) * n;
}
```
- 檔案2名稱`main.c`
```c
#include　<stdio.h>;
#include　<unistd.h>;

int factorial (int n);
int main (int argc, char **argv)
{
　　int n;

　　if (argc < 2)
　　{
　　　　printf ("Usage: %s n\n", argv [0]);
　　　　return -1;
　　}
　　else
　　{
　　　n = atoi (argv[1]);
　　　printf ("Factorial of %d is %d.\n", n, factorial (n));
　　 }
　　return 0;
}
```

利用如下的命令可編譯生成可執行文件，並執行程序
```
gcc -o factorial main.c factorial.c
./factorial 5
```

輸出結果
```
Factorial of 5 is 120.
```

## 參考資料
- Linux/UNIX高級編程
中科紅旗軟件技術有限公司編著，清華大學出版社出版
- [GCC online documentation](https://gcc.gnu.org/onlinedocs/)