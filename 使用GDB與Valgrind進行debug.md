# 使用GDB與Valgrind進行debug
###### tags: `code` `C` `debug`
###### 撰寫時間 : 2021/08/27


文章草稿
- 文章 [How do I use valgrind to find memory leaks?](https://stackoverflow.com/questions/5134891/how-do-i-use-valgrind-to-find-memory-leaks)
- 影片 [Using Valgrind and GDB together to fix a segfault and memory leak](https://www.youtube.com/watch?v=8JEEYwdrexc)



案例:在建構時向`heap`區申請空間，卻沒有在構析函數時釋放
```
g++ -o main -Wall -ggdb3 main.cpp
valgrind --leak-check=full ./main
```
此時`terminal`可顯示可能出錯在第幾行。
![](https://i.imgur.com/zQeCQyv.jpg)
完成`debug`後
```
file main
```
結尾出現`..., with debug_info, not stripped`
在輸入以剝掉一些符號和除錯訊息。
```
strip hw26
```
