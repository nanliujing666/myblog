---
title: 使用hugo创建博客方法总结

date: 2026-01-25T14:30:52+08:00
lastmod: 2026-01-25T14:30:52+08:00
cover: /images/cover/hugo.png
---
### hugo本体下载
&ensp;&ensp;hugo是一个程序，会将配置文件和模板转化为静态文件，放到public中，这是所有自动部署的原理，如Netflix会通过读取netlify.toml中的配置自动使用正确的软件构建public

&ensp;&ensp;由于apt安装不到124版本，我使用了解压安装包的方法安装
```bash
tar -xzf hugo_extended_0.124.0_linux-amd64.tar.gz hugo # 注意修改为所下载的版本

sudo mv -f hugo /usr/local/bin/

sudo chmod +x /usr/local/bin/hugo

hugo version # 验证是否成功
```

### 模板
&ensp;&ensp;我直接使用了hugo-reimu-template的完整项目，除了需要处理一下git，其他都很简单


### 个性化
&ensp;&ensp;别人的模板如果不满意，可以修改别人的模板文件来个性化，这需要你有前端三件套的知识


&ensp;&ensp;简单的方法是在页面中选择你需要改变的元素右键检查，查看这个元素的id或者class，然后在文件中搜索这个id或class，更改为你所想要的样式
