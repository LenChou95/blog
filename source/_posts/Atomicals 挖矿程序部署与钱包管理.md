---
title: Atomicals 挖矿程序部署与钱包管理
date: 2023-12-27 01:13:00
categories: 
- [Atomicals]
tags: 
- [Atomicals]
description: 零基础 Atomicals 挖矿程序部署与钱包管理教程，帮助你从零开始获取 Atomicals BTC 铭文资产。
permalink: atomicals-mining.html
---

## 部署
1. 安装 [Node.js](https://nodejs.org/en)
2. `git clone https://github.com/atomicals/atomicals-js.git`
3. `cd atomicals-JavaScript`
4. `npm install -g typescript`
5. `npm run build`
6. `npm install -g yarn`
7. `yarn install`
8. `yarn cli wallet-init` //这是创建钱包命令

最后一步是创建钱包，命令运行后，会在文件夹内生成一个 wallet.json 文件，保存着助记词和私钥，请务必保存好该文件。

创建钱包后，会自动生成两个地址，Primary Address 及 Funding Address：

**Primary**：用于接收Atomicals生态资产
**Funding**：用于铸造（挖矿）过程的中转钱包，通常是往 Funding 地址中存入相应数量的 BTC，用于铸造相应资产。

## 常用指令
### 铸造 FT 命令：
`yarn cli mint-dft dmint --satsbyte 30`

`yarn cli mint-dft quark --satsbyte=100`

dmint 和 quark 是 token 名称，请修改成相对应 FT 资产名称。
satsbyte 是矿工费设置，设置 100 即为 100聪/KB 的费用 Mint 对应资产。

### 铸造图片NFT命令：
`yarn cli mint-nft "\punk0000.png" --satsbyte 30 --satsoutput 1000 --bitworkc 233`


### 查询余额命令：
`npm run cli balances`