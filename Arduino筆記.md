# Arduino筆記
###### tags: `arduino`
###### 撰寫時間 : 2021/09/27

## 與C/C++的不同之處
### 差別
Arduino sketch是一個客製化`C/C++`的語言，可以說是`C/C++`的subset，但還是有一些需要注意的點:
- 由於這是微處理機，不支援多線程等複雜程式。
- 內建不支援C++的STL，但可以調用[第三方函式去實現](https://roboticsbackend.com/arduino-stl-library/)。
- 支援`OOP`(物件導向)。
- 在主程式檔案`*.ino`不需要包含`#include <Arduino.h>`，因為IDE會自動幫你包含，但其他檔案必須包含。
- 與`int main{}`不同入口
```c
void setup() {/*程式會在一開始執行並且只會執行一次*/}
void loop() {/*無限迴圈*/}
```
- 會根據數據類型自動初始化為0、NULL。
- 不需要先自動聲明函數，但建議還是要養成習慣先聲明。
- 增加`byte`(8 bits)、`String`(class)數據類型。
- 主程式檔案名稱需要與上一級資料夾相同。
- 沒有`new, delete`關鍵字。
- 沒有`exceptions`。

### 參考資料
- [10 Things to Know About the Arduino Language](https://www.youtube.com/watch?v=JkPPGwqLVcc)
- [Arduino Object Oriented Programming (OOP)](https://roboticsbackend.com/arduino-object-oriented-programming-oop/)


<br><br>


## 函式庫
### 介紹
跟一般寫`C/C++`還是不太一樣，一開始編譯時一直想不透他incude library的path，Arduino IDE有動一些手腳。

### 標準函式庫
例如以下屬於標準函式庫，可以不指定路徑直接使用:
```c
#include <Arduino.h>
#include <Server.h>
```
原始路徑位於:
```
{安裝路徑}\Arduino\hardware\arduino\avr\cores\arduino
```

### 自定義/第三方函式庫
傳統`C/C++`寫法指定路徑，新增`*.c`,`*cpp`,`*h`(官方似乎較推薦`OOP`寫法)。
匯入時不能用`<>`引入，而是用`""`
```c
#include "my_lib.h"
```
可以讓函式庫成為arduino的lib，加上成功後就可用`<>`方式引入頭文件，路徑位於:
```
{安裝路徑}\Arduino\libraries
```
裡面的`*txt`檔為使Arduino IDE能對自定義庫做syntax highlight，與語法如下:
|代碼|解釋|
|:-:|:-:|
|`#`|註釋|
|`KEYWORD1`|highlight類名|
|`KEYWORD2`|highlight方法名|
|`LITERAL1`|highlight常量|

### 分文件編寫
- main.ino(**上一層資料夾名稱為main**)
```cpp
// This examples shows how to blink a LED
// using the Led class from the Led library

#include "Led.h"
// Use the built-in LED
#define LED_PIN 13
// Create a Led object
// This will set the pin to OUTPUT
Led led(LED_PIN);
void setup() { }
void loop() {
    // Power on the LED
    led.on();
    delay(1000);
    // Power off the LED
    led.off();
    delay(1000);
}
```

- Led.cpp
```cpp
#include "Led.h"
Led::Led(byte pin) {
  this->pin = pin;
  init();
}
void Led::init() {
  pinMode(pin, OUTPUT);
  off();
}
void Led::on() {
  digitalWrite(pin, HIGH);
}
void Led::off() {
  digitalWrite(pin, LOW);
}
```
- Led.h
```cpp
//include guard(not support #pragma once)
#ifndef MY_LED_H
#define MY_LED_H
#include <Arduino.h>
class Led {
  
  private:
    byte pin;
    
  public:
    Led(byte pin);
    void init();
    void on();
    void off();
};
#endif
```

### 參考資料
- [What’s the deal with Arduino.h?](https://forum.arduino.cc/t/whats-the-deal-with-arduino-h/273932)
- [Arduino自定義庫的編寫](https://www.itread01.com/content/1550524705.html)
- [Create Your Own Arduino Library](https://roboticsbackend.com/arduino-create-library/)
- [官方doc - Libraries](https://www.arduino.cc/reference/en/libraries/)
