---
title: vim使用教程 
description: 简述vim的各种快捷命令 
date: 2026-01-30T12:30:52+08:00
lastmod: 2026-01-30T12:30:52+08:00
cover: /images/cover/vim.png
mermaid: True
tags:
  - vim 
categories:
  - 计算机技术
---

## vscode设置
```json
"vim.insertModeKeyBindings": [
        {
            "before": ["j", "j"],
            "after": ["<Esc>"],
            "timeout": 50  
        }//将esc改为jj，这样在插入模式中按两次jj就可以变为普通模式
    ],
    "vim.handleKeys": {
        "<C-a>": false,
        "<C-f>": false,
        "<C-n>": false
    }//关闭vim的一些快捷键，保留原生快捷键


```

## 光标移动
```keyboard
h j k l  左 下 上 右 移动光标

gg 跳转到开头
G 跳转到结尾

0 跳转到行首
$ 跳转到行尾

^ 跳转到行首第一个非空字符
```

## 文本处理
```keyboard
dd 删除整行
x 删除单字符

yy 行复制
p 行粘贴

u 撤销操作


```

## 查询
```
/+查询内容 可全局查询

n 查找下一个

N 查找上一个
```


