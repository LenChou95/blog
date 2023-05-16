---
title: 如何绕过烦人的 hCaptcha 验证
date: 2023-05-17 04:15:00
category: skill
tags:
    - tool
    - hcaptcha
permalink: disabling-hcaptcha.html
index: false
---

## 什么是 hCaptcha？
hCaptcha 是一种人类验证服务，类似于 Google reCAPTCHA。它旨在识别并区分人类用户和机器人，并帮助防止常见的 Web 自动化攻击，如 DoS、恶意机器人攻击和无节制的 Web 爬取。

但 hCaptcha 对机器人有没有拦截我不清楚，对正常人类却带来了极大的不便。

## 通过无障碍服务，绕过 hCaptcha 验证
1. 通过 [这个链接](https://dashboard.hcaptcha.com/signup?type=accessibility) 注册无障碍服务，请填写真实可用的邮箱地址；
2. 使用邮箱收件，通过邮件中的「Get Accessibility Cookie」按钮打开链接，请注意链接应该是如下例子这样：
`https://accounts.hcaptcha.com/verify_email/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

3. 通过链接获取 hCaptcha Cookie
- 点击按钮将会跳转到 hCaptcha 的设置页面
- 点击「Set Cookie」按钮，等按钮下方出现一行字「Cookie set.」时就完成了

当下一次再遇到 hCaptcha 只需要点击验证框即可，不用再进行烦人的图片验证了

【注】hCaptcha 官方其实也对无障碍服务做了说明[具体请查阅这里](https://www.hcaptcha.com/accessibility)