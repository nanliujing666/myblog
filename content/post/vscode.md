---
title: vscode设置
description: 保存vscode的设置
date: 2026-03-17T10:30:52+08:00
lastmod: 2026-03-17T10:30:52+08:00
cover: /images/cover/vscode.ico
mermaid: True
tags:
  - vscode
  - 备份
categories:
  - 计算机技术
---


vscode基础设置
```JSON

    "workbench.colorTheme": "Quiet Light",
    "editor.fontSize": 24,
    "remote.SSH.remotePlatform": {
        "192.168.233.105": "linux"
    },
    "files.autoSave": "afterDelay",
    "git.autofetch": true,
    "git.confirmSync": false,
    "vim.digraphs": {

    },
    "editor.cursorSmoothCaretAnimation": "on",
    "editor.cursorBlinking": "smooth",
    "workbench.list.smoothScrolling": true,
    "editor.smoothScrolling": true,
    "terminal.integrated.smoothScrolling": true
```

***
好用的插件

| 插件名 | 说明 |
|--------|------|
| better-comments | 更好的代码注释高亮 |
| anthropic.claude-code | Claude Code AI 助手 |
| ms-ceintl.vscode-language-pack-zh-hans | 简体中文语言包 |
| ms-python.python | Python 支持 |
| ms-python.vscode-pylance | Python 语言服务器 |
| ms-vscode-remote.remote-ssh | SSH 远程开发 |
| njpwerner.autodocstring | 自动生成文档字符串 |
| vscodevim.vim | Vim 键位支持 |


***


1，autoDocstring具体设置

使用方法：

输入"""就可以自动出现函数注释
```JSON
    "autoDocstring.docstringFormat": "google",
    "autoDocstring.customTemplatePath": "",
    "autoDocstring.startOnNewLine": true,
    "autoDocstring.generateDocstringOnEnter": true,
    "autoDocstring.includeExtendedSummary": false,
    "autoDocstring.includeName": true,
    "autoDocstring.guessTypes": true,
```
修改模板文件

文件地址C:\Users\用户\.vscode\extensions\njpwerner.autodocstring-0.6.1\out\docstring\templates



2，Better Comments具体设置

"!"表示警告、"?"表示询问，"TODOs"表示待办事项，"*"表示高亮内容