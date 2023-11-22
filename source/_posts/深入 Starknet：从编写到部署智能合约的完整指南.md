---
title: 浅入 Starknet：从编写到部署智能合约完整笔记
date: 2023-02-10 21:00:00
categories: 
- [Starknet]
tags: 
- [coding]
description: Starknet 作为一个强大的 Layer 2 扩展解决方案，提供了在以太坊生态系统中编写和部署高效智能合约的独特方法。由于我最近也在学习 Starknet 的智能合约开发，简单写一篇文章记录最基础的智能合约编写、测试和部署过程。
permalink: starknet-contract.html
---
Starknet 作为一个强大的 Layer 2 扩展解决方案，提供了在以太坊生态系统中编写和部署高效智能合约的独特方法。由于我最近也在学习 Starknet 的智能合约开发，简单写一篇文章记录最基础的智能合约编写、测试和部署过程。

## 准备工作
在开始之前，确保你已经熟悉 Solidity 或 Vyper，并且有一些基本的智能合约开发经验。此外，你需要安装 Node.js 和 npm。

## 第一步：配置环境
首先，安装 Starknet 开发环境。Starknet 使用 Cairo 语言编写智能合约，这是一个专门为 zk-STARKs 设计的编程语言。你可以从以下网址下载和安装 Cairo 语言和其开发工具：[Cairo 语言官方文档](https://www.cairo-lang.org/)

## 第二步：编写智能合约
以下是一个简单的 Starknet 智能合约示例，它实现了一个基本的计数器：

<pre><code>%lang starknet

@storage_var
func counter() -> (value: felt):
end

@external
func increment():
    let (current_value) = counter.read()
    counter.write(current_value + 1)
    return ()
end
</code></pre>

## 第三步：编译合约
使用 Cairo 编译器编译你的合约。在命令行中运行以下命令：
<pre><code>starknet-compile contract.cairo --output contract_compiled.json --abi contract_abi.json</code></pre>
 这将生成合约的编译版本和 ABI 文件

## 第四步：部署合约
接下来，需要将合约部署到 Starknet 测试网。首先，安装 Starknet CLI 工具，然后运行以下命令来部署合约：
<pre><code>starknet deploy --contract contract_compiled.json --network alpha</code></pre>
 部署成功后，你将获得一个部署地址。

## 第五步：与合约交互
现在合约已经部署，你可以通过 Starknet CLI 或其他工具与其交互。例如，调用 `increment` 函数：
<pre><code>starknet invoke --address [合约地址] --abi contract_abi.json --function increment</code></pre>

## 第六步：测试和验证
测试是任何智能合约开发的重要部分。你可以使用 Starknet 提供的测试框架来编写和运行测试。详细的测试指南和框架可以在 [Starknet 文档](https://docs.cairo-lang.org/) 中找到。

## 结语
以上步骤提供了在 Starknet 上开发和部署智能合约的基本概览。Cairo 和 Starknet 生态系统正在快速发展，不断有新的工具和资源出现。持续学习和实践是掌握 Starknet 智能合约开发的关键。

