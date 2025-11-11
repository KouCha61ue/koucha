---
title: 'GCCとClangについて'
date: 2025-11-12T05:14:01+09:00
draft: false
image: ''
categories:
  - ソフトウェアエンジニアリング
tags:
  -
---

# 1. 概要
GCCとClangのコンパイルのやり方は超初歩的であるはずですが、わたくしはちょくちょく忘れてしまうことがありメモをしました、なので共有したいと思う。

# 2. 基本

```
コンパイラ ソースコード -o 出力ファイル
```
# 3. コンパイル方法
## 3.1. GCC
```bash
#Cの場合
gcc main.c -o main

#C++の場合
g++ main.c -o main
```
## 3.2. Clang
```bash
#Cの場合
clang main.c -o main

#C++の場合
clang++ main.c -o main
```

-o を付けなかった場合、出力は a.out（Linux/macOS）または a.exe（Windows）になる。

# 4. 実行方法

```bash
./main
```
