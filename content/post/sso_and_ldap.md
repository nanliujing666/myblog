---
title: 单点登录与账号通用的原理
description: 使用简易示意图介绍了sso和ldap时，几个身份的数据沟通方式
date: 2026-03-13T14:30:52+08:00
lastmod: 2026-03-13T14:30:52+08:00
cover: /images/cover/sso.png
mermaid: True
tags:
  - sso
  - ldap
  - 系统架构
  - web
categories:
  - 计算机技术
---


## 简述
单点登录 (Single sign-on, SSO) 是一种认证 (Authentication) 方法，允许用户使用一组凭据访问多个系统。


常用有两种SSO方式：1，基于 SAML 的 SSO；2，基于 OIDC 的 SSO。本文主要使用基于 OIDC 的 SSO。


OIDC 相比之下，建立在 OAuth 2.0 之上，提供了一种更现代的 SSO 方法。它使用JSON Web Token (JWT) 在 IdP 和 SP 之间交换身份信息，提供增强的安全性和更大的灵活性。
## 流程
```mermaid
  sequenceDiagram
  participant 浏览器（用户）
  participant 网页服务器
  participant sso服务器
  participant ldap服务器
  浏览器（用户）->>网页服务器:用户点击sso登陆接口
  网页服务器->>浏览器（用户）:带上state字段，302重定向到SSO登录的接口
  浏览器（用户）->>sso服务器:访问sso登录页面
  sso服务器->>sso服务器:检查用户是否已经登录,如果登录了则没有下面的两个流程
  sso服务器->>浏览器（用户）:发送登录页
  浏览器（用户）->>sso服务器:登录
  sso服务器->>ldap服务器:查询LDAP服务器，创建登陆会话
  sso服务器->>浏览器（用户）:重定向到网页服务器注册到sso的回调地址，同时会携带code，state
  浏览器（用户）->>网页服务器:访问回调地址
  网页服务器->>sso服务器:用code换取SSO token
  sso服务器->>浏览器（用户）:返回SSO token，这个token只用于识别用户，内部包含用户uid等数据
  网页服务器->>浏览器（用户）:网页服务器得到了用户id，此时服务器已经完成了认证，之后可根据不同情况自己选择token或者cookie等鉴权方法
  
```
## 理解
SSO登录对于网页服务器来说，其实和普通的登录没有什么区别


在正常的登录中，用户发送账号和密码，后端拿到之后要去数据库调用验证


而在SSO中，用户发过来的是code，后端需要拿到sso服务器去做验证


网页服务器需要提供两个接口，一个是登录接口，一个是回调接口。这两个接口其实对应着两个不同的登录方式，如果用户使用登录接口，就是传统登录，如果使用回调接口就是sso。在设计时，前端页面应该有一个按钮之类的东西，让用户选择。





