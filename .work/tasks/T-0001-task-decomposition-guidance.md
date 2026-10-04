---
id: T-0001
title: 課題の分解基準を明文化する
status: in_review
priority: medium
project: null
depends_on: []
created: 2026-10-04
updated: 2026-10-04
---

## 目的

課題を分割するかまとめるかの判断基準を明確にし、細かすぎる分割と大きすぎる課題を避ける。

## 完了条件

- [x] `.agents/docs/03-workflow.md`に、分割する場合とまとめる場合の目安を記載する。
- [x] 利用者から確認できる成果を基本単位とし、依存関係とテストの扱いを明記する。
- [x] Markdown構造と`git diff --check`を検証する。

## 進捗

- 2026-10-04: 分割基準を作業フローへ追記。見出し番号、Markdownフェンス、課題front matter、`git diff --check`の検証に合格。独立AIレビューはAPPROVE（指摘なし）。

## ブロッカー・次の作業

- ブロッカー: なし
- 次の作業: PRを作成してユーザー確認を依頼する。
