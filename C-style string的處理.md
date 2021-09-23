# C-style string的處理
###### tags: `C` `code`
###### 撰寫時間 : 2021/08/29

## 前言
注意此部分與`C++`的標頭檔`string`(屬於OOP中的class)不同。`C`語言使用`string.h`；`C++`沿用`C`使用`cstring`。

## 函數
### 計算類型函數
- size_t (資料型態)<br>
Unsigned integral type，32位元4bytes；64位元8bytes


- NULL<br>
等於`\0`，而\是跳脫字元(脫離原字元的意思)


- strlen (長度)
`size_t strlen( const char *str );` 傳入一個字串 str，回傳這個字串的長度，而 '\0' 不計入長度（但 '\n' 計入）。其中的回傳值型態 size_t 通常是無號整數型別。

---

### strcpy (複製)
```cpp
char * strcpy ( char * destination, const char * source );
```
1. 功能: 將 source 的值複製給 destination。不能用`=`指派字串，要用`strcpy`。
2. 型態: `const char * source`不代表一定要指派`const`，而是告訴使用者，所指派的值不會被變動。
等同於:
```cpp
const char *sou1 = new char[11];
const char *sou2 = sou1;
```
3. 範例
```cpp
char *str1 = "C programming";
char str2[20];
strcpy(str2, str1);
```
4. 範例2<br>
由於`des`儲存的是第一個位置，因此當想替換字串
`Hi, I am Mary` -> `Hi, I am John`
```cpp
char *ch = new char[21];
strcpy(ch, "Hi, I am Mary");
char newname[] = "John";
strcpy(ch + strlen(ch) - strlen(newname), newname);
std::cout << ch << std::endl;
```


### strcat (串接)
1. 功能: 將 source 的內容，串接在 destination 原先內容的後面。
2. 型態: `char * strcat ( char * destination, const char * source );`
3. 範例:
```cpp
char word[1000] = "1234";
strcat(word, "567");
std::cout << word << std::endl;
```

### strcmp (比較)
1. 功能: 從第一個字元開始逐一比對 str1 與 str2 的所有字元。比對過程若有不一樣的字元時：

|ASCII比對|結果|
|:-:|:-:|
|str1 > str2|正值|
|str1 < str2|負值|
|str1 == str2|0|
2. 型態: `int strcmp ( const char * str1, const char * str2 );`
3. 範例:
```cpp
char word1[] = "abcd";
char word2[] = "Abcd";
int i = strcmp(word1, word2);
```

<br>

### strstr (尋找)
1. 功能: 運算出 str2 在 str1 中第一次出現的位置。若不存在結果為 NULL。
2. 型態: `const char * strstr ( const char * str1, const char * str2 );`
3. 範例:
```cpp
char word1[] = "33551saber";
char *pc = strstr(word1, "551");
std::cout << pc << std::endl;
//輸出是551saber，因為字串取值會取到空字元
```

### strtok (切割)
1. 功能: 依照 delimiters 的內容切割 str。delimiters 中的各個字元為或的關係。str 的內容會被改變。
2. 型態: `char * strtok ( char * str, const char * delimiters );`
3. 範例:
```cpp
char work[] = "abc,def,ghi.hfd";
char *tok = strtok(work, ",."); //"或"的關係
while(tok != NULL){ //NULL = /0(結束的控制字元)
    tok = strtok(NULL, ",."); //剩下的字符數組要使用NULL讀取
}
```

### 練習
1. 題目: 讀取`"{70, 12, 20, 50}"`，並儲存為**整數數列**
2. 個人解答:
```cpp
#include <iostream>
#include <cstring>

int main() {
	char work[] = "{70, 12, 20, 50}";
	char *work2 = new char[strlen(work)];
	strcpy(work2, work); //避免更改到原本的字符數組，因此進行複製
	int arr[10];
	int i=0;

	char *tok = strtok(work2, "{}, "); //delimiters 中的各個字元為"或"的關係
	while(tok != NULL){ //NULL = /0(結束的控制字元)
		arr[i++] = atoi(tok); //將字符數組轉換為int
		tok = strtok(NULL, "{}, "); //剩下的字符數組要使用NULL讀取
	}

	delete work2; //釋放heap空間，以免mem leak

	for (int j=0; j<i; j++){  //印出測試
		std::cout << arr[j] << std::endl;
	}
	return 0;
}
```

## 參考
- [Cpp Road中文教學](https://www.youtube.com/channel/UC9Jk6B_ROKowxzXoQAuR6tA)
- [cplusplus網站](https://www.cplusplus.com/reference/cstring/)
- [programiz](https://www.programiz.com/c-programming/library-function/string.h/strcat)