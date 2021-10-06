# C++的inline, extern, static關鍵字
###### tags: `code` `c++`
###### 撰寫時間 : 2021/09/29

## inline(內嵌函數)
### 介紹
一般呼叫函數，電腦的機器語言指令會紀錄目前工作階段的記憶體位址，然後跳至函數的記憶體位置處理完程序後，並回到原先的位址上，而這樣來回會造成時間上的額外負擔。

`C++`於是提供這種內嵌函數，當我們加入關鍵字時，在編譯時便會把函數中的程式直接展開。

### 注意
1. 即便加入inline想要使用內嵌函數，編譯時也不一定就會實作，視編譯器優化而定。
2. 類中定義的所有函數都是隱式內聯的，但最好的寫法還是類內寫原型，類外函數指定為`incline`
```cpp
class S{
public:
    int square(int s); // declare the function
};
  
inline int S::square(int s){ // use inline prefix
}
```

### 與C的macro展開差異
macro由預處理器管理，內聯函數由`C++`編譯器管理。而macro無法訪問類內私有成員。

## extern
### 介紹
- 聲明extern關鍵字的全局變量和函數可以使得它們能夠**跨文件被訪問**。
- `extern "C"`<br>
`C++`支援函數重載，而`C`則不支援。函數被`C++`編譯後在符號庫中的名字與C語言的不同，因此使用`extern "C"{}`，可以讓`C++`在引用`C`時不會多加處理(`mangled name`)，而能正常使用。

## static
### 介紹
- 兩個 compile 後的 .o 檔在 link 的過程中就會因為名字相同而產生衝突的錯誤。對不存在在 funciton 外的變數來說，基本上都是 global variable，static 的用意就是要讓這樣的 global 只限定在該檔案內，而不是整個程式中。
- static 出現在 class 的 member variable 的意思是該 variable 並不屬於某個 instance，他屬於這個 class，所有以此 class 生成出來的 instance 都共用這個 variable。

## 參考資料
- [Inline Functions in C++](https://www.geeksforgeeks.org/inline-functions-cpp/)
- [C/C++ 中的 static, extern 的變數](https://medium.com/@alan81920/c-c-%E4%B8%AD%E7%9A%84-static-extern-%E7%9A%84%E8%AE%8A%E6%95%B8-9b42d000688f)
- [C++中extern C含義深層探索](https://b8807053.pixnet.net/blog/post/3612202)
- [extern “C” 如何使系統函式庫兼容C與C++](https://hackmd.io/@rhythm/HyOxzDkmD)