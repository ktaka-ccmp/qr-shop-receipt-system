# Freedom to Operate（FTO）調査

**最終更新:** 2026年2月5日

---

## 概要

本ディレクトリは、QR Shop Receipt Systemの実装において**他社特許を侵害しないための調査資料**をまとめたものです。

---

## 読み方ガイド

| 順番 | ファイル | 内容 | 対象読者 |
|------|---------|------|---------|
| **1** | [summary.md](summary.md) | 調査結果の総合サマリー | 全員 |
| **2** | [avoidance-checklist.md](avoidance-checklist.md) | 実装禁止事項のチェックリスト | 開発者 |
| **3** | [expiry-timeline.md](expiry-timeline.md) | 特許有効期限一覧 | 経営・法務 |

---

## 詳細レポート

| ファイル | 内容 |
|---------|------|
| [reports/toshiba-tec.md](reports/toshiba-tec.md) | 東芝テック特許（最重要） |
| [reports/freee.md](reports/freee.md) | freee特許（勘定科目自動判定） |
| [reports/pos-vendors.md](reports/pos-vendors.md) | POSレジベンダー（Airレジ、スマレジ、Square） |
| [reports/qrcode.md](reports/qrcode.md) | QRコード関連技術 |
| [reports/e-bookkeeping.md](reports/e-bookkeeping.md) | 電子帳簿保存法関連 |
| [reports/hitachi.md](reports/hitachi.md) | 日立グループ |
| [reports/citation-network.md](reports/citation-network.md) | 引用特許ネットワーク |
| [reports/prior-art-non-patent.md](reports/prior-art-non-patent.md) | 公知例（非特許DB） |

---

## 結論サマリー

### 回避必須の機能（実装禁止）

| 機能 | 関連特許 | 有効期限 |
|------|---------|---------|
| ハイライト表示（色・背景変更） | 東芝テック 6598936 | 2034年頃* |
| 返品連動の自動訂正レシート | 東芝テック 6618585 | 2033年頃* |
| キーワード対応テーブルによる勘定科目自動判定 | freee 5503795 | 2033年頃 |

*有効期限はJ-PlatPatで要確認

### 安全に実装可能な機能

- 電子領収書の発行・保存・配信
- QRコードによる店舗-利用者連携（MPM/CPM共に基本的にOK）
- タイムスタンプ付与（RFC3161準拠）
- 訂正削除履歴管理
- PDF/CSVエクスポート
- 会計ソフト連携（勘定科目判定は会計ソフト側）

---

## 調査方法論

### 調査目的

1. 本ビジネスアイデアに関連する特許を網羅的に調査
2. 各特許の有効期限を確認し、特許切れの技術を特定
3. 請求項を解析し、ビジネスプランへの該当/非該当を判定
4. 回避すべき実装を明確化
5. 公知例（拒絶された出願、補正履歴等）を蓄積

### 調査対象技術領域

| No | 構成要素 | 関連技術キーワード |
|----|----------|-------------------|
| 1 | QRコードによる店舗/利用者識別 | QRコード、バーコード、消費者コード |
| 2 | 電子レシート/領収書発行 | 電子レシート、電子領収書、デジタルレシート |
| 3 | ワンタイムトークン認証 | ワンタイムトークン、一時認証、セッション管理 |
| 4 | 電子帳簿保存法対応 | 電子帳簿、タイムスタンプ、訂正削除履歴 |
| 5 | 勘定科目自動判定 | 自動仕訳、勘定科目、経費分類 |
| 6 | POSレジ連携 | POS、レジ、決済連携 |
| 7 | 経費精算システム連携 | 経費精算、会計連携、CSV出力 |

### 調査対象出願人と調査状況

| 出願人 | 関連サービス | 優先度 | 調査状況 | レポート |
|--------|-------------|--------|----------|---------|
| 東芝テック | スマートレシート | 最高 | ✅ 完了 | [reports/toshiba-tec.md](reports/toshiba-tec.md) |
| freee | freee会計 | 高 | ✅ 完了 | [reports/freee.md](reports/freee.md) |
| リクルート | Airレジ | 高 | ⚠️ 概要のみ | [reports/pos-vendors.md](reports/pos-vendors.md) |
| スマレジ | スマレジ | 高 | ⚠️ 概要のみ | [reports/pos-vendors.md](reports/pos-vendors.md) |
| 日立グループ | POS/決済関連 | 高 | ✅ 完了 | [reports/hitachi.md](reports/hitachi.md) |
| Square | Square | 中 | ⚠️ 概要のみ | [reports/pos-vendors.md](reports/pos-vendors.md) |
| デンソーウェーブ | QRコード | 中 | ✅ 完了 | [reports/qrcode.md](reports/qrcode.md) |
| NEC | POS関連 | 中 | ❌ 未調査 | - |
| 富士通 | POS関連 | 中 | ❌ 未調査 | - |

### 調査フェーズと実施状況

| Phase | 内容 | 状況 | 成果物 |
|-------|------|------|--------|
| 1 | 主要出願人の特許調査 | ✅ 完了 | reports/*.md |
| 2 | 技術分野別の網羅的調査 | ⚠️ 部分的 | - |
| 3 | 有効期限確認 | ✅ 完了 | [expiry-timeline.md](expiry-timeline.md) |
| 4 | 請求項詳細解析 | ✅ 完了 | [summary.md](summary.md) |
| 5 | 引用特許・公知例調査（特許DB） | ✅ 完了 | [reports/citation-network.md](reports/citation-network.md) |
| 6 | 公知例調査（非特許DB） | ✅ 完了 | [reports/prior-art-non-patent.md](reports/prior-art-non-patent.md) |

### 調査データベース

| データベース | 用途 | URL |
|-------------|------|-----|
| J-PlatPat | 日本特許の検索・経過情報確認 | https://www.j-platpat.inpit.go.jp/ |
| Google Patents | 横断検索、特許全文 | https://patents.google.com/ |
| USPTO | 米国特許（参考） | https://www.uspto.gov/ |
| Espacenet | 欧州特許（参考） | https://worldwide.espacenet.com/ |

---

## 残課題

| 優先度 | 課題 | 備考 |
|--------|------|------|
| 高 | Airレジ/スマレジの詳細特許調査 | J-PlatPatでの出願人検索が必要 |
| 高 | 東芝テック特許の有効期限確認 | 分割出願の可能性、J-PlatPatで要確認 |
| 中 | Square/Block米国特許調査 | USPTOでの調査が必要 |
| 中 | NEC/富士通のPOS関連特許 | 優先度に応じて実施 |

---

## 注意事項

- 本調査はWeb検索ベースの予備調査です
- 正確な有効期限・権利状態はJ-PlatPatで確認してください
- 最終判断は弁理士・弁護士に相談してください
