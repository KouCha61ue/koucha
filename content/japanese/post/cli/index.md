---
title: 'CLIドキュメント'
date: 2025-06-25T01:22:01+09:00
draft: false
image: ''
categories:
  -
tags:
  - メモ
---

※これは個人的なメモです。

## 概要
CLIツールのドキュメント（随時追加予定）


## 🚀 fd — Simple · Fast · User-friendly `find` 代替

| 基本構文 | <code>fd&nbsp;[PATTERN]&nbsp;[PATH]&nbsp;[OPTIONS]</code> |
|----------|----------------------------------------------------------|
| デフォルト | PATTERN は **正規表現** / PATH 省略で **カレント dir** |
| 特徴 | 隠しファイル除外・シンタックスカラー・マルチスレッド検索 |

### 🔑 代表例

| 目的 | コマンド |
|------|---------|
|`hello` を含むファイル | `fd hello` |
|ホーム直下から `config` 検索 | `fd config ~` |
|拡張子 `.txt` を検索 | `fd '.txt$'` |

<details><summary>📜 主なオプション</summary>

| オプション | 意味 |
|-----------|------|
|`-H / --hidden`|隠しファイルも対象|
|`-I`| `.gitignore` 無視|
|`-t f / -t d`|ファイル / ディレクトリのみ|
|`-e <ext>`|拡張子検索（例 `-e rs`）|
|`-x <cmd> {}`|結果にコマンド適用|

</details>

> **順序は自由** — `fd -H config ~` のように OPTION を前にしても OK。

---

## ⚡ fzf — Anything-to-Anything Fuzzy Finder

### 1️⃣ 基礎コマンド

| 目的 | コマンド例 |
|------|-----------|
|テキストリストから選択|`cat list.txt \| fzf`|
|履歴検索|`history \| fzf`|
|Git 管理下ファイルを検索|`git ls-files \| fzf`|
|プロセス選択|`ps aux \| fzf`|
|クリップボードへ送る|`some_command \| fzf \| pbcopy`|

### 2️⃣ キーバインド（シェル統合）

| キー | デフォルト動作 |
|------|---------------|
|<kbd>Ctrl T</kbd>|ファイル選択 → パスを挿入|
|<kbd>Ctrl R</kbd>|履歴検索 → コマンド貼り付け|
|<kbd>Alt C</kbd>|ディレクトリ選択 → `cd`|

### 3️⃣ カスタム：fd を使う <kbd>Ctrl T</kbd>

# ~/.zshrc
export FZF_CTRL_T_COMMAND='fd --type f --hidden --follow --exclude .git'
