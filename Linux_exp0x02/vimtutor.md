## VIMTUTOR操作

- Lesson 1

  [![asciicast](https://asciinema.org/a/PjzWdmZ9N6jpiP843B5BdL2qB.svg)](https://asciinema.org/a/PjzWdmZ9N6jpiP843B5BdL2qB?t=0)

- Lesson 2

  [![asciicast](https://asciinema.org/a/8JLCWQR0dhDCahzPb6JyDUbn3.svg)](https://asciinema.org/a/8JLCWQR0dhDCahzPb6JyDUbn3?t=10)

- Lesson 3

  [![asciicast](https://asciinema.org/a/08PBQDiOdor508nXGcYF1EHbC.svg)](https://asciinema.org/a/08PBQDiOdor508nXGcYF1EHbC?t=18)

- Lesson 4
  [![asciicast](https://asciinema.org/a/8M1q0wefnk6k2vnQnCP07ZR7G.svg)](https://asciinema.org/a/8M1q0wefnk6k2vnQnCP07ZR7G?t=18)

- Lesson 5
  [![asciicast](https://asciinema.org/a/OhyNKK7X1ALUvPSJDwVNHJ81o.svg)](https://asciinema.org/a/OhyNKK7X1ALUvPSJDwVNHJ81o?t=21)

- Lesson 6
  [![asciicast](https://asciinema.org/a/NpTpAawBf21Xl5OCyHF1UPOr2.svg)](https://asciinema.org/a/NpTpAawBf21Xl5OCyHF1UPOr2?t=25)

- Lesson 7
  [![asciicast](https://asciinema.org/a/WRd1ZJ2rMA7b1VHbI2lNU9FVc.svg)](https://asciinema.org/a/WRd1ZJ2rMA7b1VHbI2lNU9FVc)

## VIMTUTOR自查清单

- vim的工作模式

  ```
  Normal mode
  Visual mode
  Insert mode
  ```

- Normal模式下，从当前行开始，一次向下移动光标10行的操作方法？如何快速移动到文件开始行和结束行？如何快速跳转到文件中的第N行？

  - 一次向下移动光标10行:```10j```
  - 快速移动到文件开始行:```gg```
  - 快速移动到文件结束行:```G```
  - 快速跳到第N行:```NG```

- Normal模式下，如何删除单个字符、单个单词、从当前光标位置一直删除到行尾、单行、当前行开始向下数N行？

  - 删除单个字符:```x```
  - 删除单个单词:```dw```
  - 从光标位置一直删除到行尾:```d$```
  - 删除单行:```dd```
  - 删除当前开始向下N行:```dNd```

- 如何在vim中快速插入N个空行？如何在vim中快速输入80个-？

  - 快速插入N个空行:
    - 插入到下方:```10o```
    - 插入到上方:```10O```
  - 快速输入80个-：```80i-ESC```

- 如何撤销最近一次编辑操作？如何重做最近一次被撤销的操作？

  - 撤销最近一次编辑操作:```u```
  - 重做最近一次被撤销的操作:```CTRL+R```

- vim中如何实现剪切粘贴单个字符？单个单词？单行？如何实现相似的复制粘贴操作呢？

  - 剪切单个字符:```x```
  - 剪切单个单词:```dw```
  - 剪切单行:```dd```
  - 复制单个字符:```v选中+y```
  - 复制单个单词:```v --> e --> y```
  - 复制单行:```v --> $ --> y```
  - 粘贴:```p```

- 为了编辑一段文本你能想到哪几种操作方式（按键序列）？

- 查看当前正在编辑的文件名的方法？查看当前光标所在行的行号的方法？

  ```CTRL+G```

- 在文件中进行关键词搜索你会哪些方法？如何设置忽略大小写的情况下进行匹配搜索？如何将匹配的搜索结果进行高亮显示？如何对匹配到的关键词进行批量替换？

  - 文件中关键字搜索:```/关键字 <ENTER> ```
  - 设置忽略大小写进行匹配:```set ic```
  - 对匹配结果高亮:```set hls```
  - 批量替换
    - 对指定行范围:```#,#s/old/new/g```
    - 对文件中所有匹配的关键字:```%s/old/new/g```

- 在文件中最近编辑过的位置来回快速跳转的方法？

  - ``

- 如何把光标定位到各种括号的匹配项？例如：找到(, [, or {对应匹配的),], or }
  - ```%```

- 在不退出vim的情况下执行一个外部程序的方法？

  - ```!+命令```

- 如何使用vim的内置帮助系统来查询一个内置默认快捷键的使用方法？如何在两个不同的分屏窗口中移动光标？

  - 查询内置默认快捷键的使用方法:```:help + 快捷键```

  - 在不同的窗口中移动光标:```CTRL w/CTRL ww```

     
