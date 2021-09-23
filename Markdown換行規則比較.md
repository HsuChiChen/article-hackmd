# Markdown換行規則比較
###### tags:`markdown`
###### 撰寫時間 : 2021/09/10


|strategy/<br>render tools|MackMD on commonMark mode|Github readme, vdcode|Github issue and comment|Typora|Reddit|
|:-:|:-:|:-:|:-:|:-:|:-:|
|only enter (hard line)|X|X|O|O|X|
|embedded html `<br>` tag|O|O|X(space one more)|O|X|
|space space enter (soft line)|O|O|O|O|O|
|backslash`\` enter (soft line)|O|O|O|X|O|


- workaround<br>
**double click space** will turn to the next paragraph.

- reference<br>
[Sync a Note with GitHub](https://hackmd.io/c/tutorials/%2Fs%2Flink-with-github)

- testing data
```
//hard line
only
enter 

//embedded html br tag
html <br> tag 

//soft line 1
space space  
enter

//soft line 2
backslash\
enter 

//others
double

enter
```