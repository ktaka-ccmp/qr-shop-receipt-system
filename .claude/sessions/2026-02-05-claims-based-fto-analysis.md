# Session Snapshot: Claims-Based FTO Analysis

**Date:** 2026-02-05
**Topic:** 請求項ベースの詳細FTO分析
**Previous Snapshot:** `2026-02-05-patent-directory-reorganization.md`

---

## Current Task

請求項ベースの詳細FTO（Freedom to Operate）分析を実施する。

---

## 方針

従来のレポート形式から、**弁理士が行うFTO調査の標準的な方法論**に変更。

| ステップ | 内容 | 状態 |
|---------|------|------|
| **1** | 関連する特許番号・公開公報番号の一覧表を作成 | ⏳ 次のタスク |
| **2** | 各特許のドキュメントを作成し、請求項をすべて転記、メタ情報を記入 | ⏳ |
| **3** | 請求項ごとに構成要件を正確に理解 | ⏳ |
| **4** | ビジネスアイデアが権利侵害するかを請求項ごとに判定 | ⏳ |
| **5** | 回避すべき事項をドキュメントに追記 | ⏳ |
| **6** | サマリドキュメントを作成/更新 | ⏳ |

### 判定原則

> **オールエレメントルール**: 請求項の**すべての構成要件**を充足する場合にのみ侵害となる

---

## ディレクトリ構成

### 変更前

```
patents/fto/
├── README.md
├── summary.md
├── avoidance-checklist.md
├── expiry-timeline.md
└── reports/               # 既存レポート8件
```

### 変更後（予定）

```
patents/fto/
├── README.md                   # 残す → 最後に更新
├── patent-list.md              # 新規: 特許番号一覧（ステップ1）
├── claims/                     # 新規: 請求項分析（ステップ2-5）
│   ├── JP6598936B2.md          # 東芝テック（ハイライト表示）
│   ├── JP6618585B2.md          # 東芝テック（返品連動）
│   ├── JP5503795B1.md          # freee（キーワード対応）
│   └── ...                     # Airレジ/スマレジ等も追加
├── summary.md                  # 残す → ステップ6で更新
├── avoidance-checklist.md      # 残す → ステップ5で更新
├── expiry-timeline.md          # 残す → ステップ2で更新
│
└── legacy/                     # 退避: 旧reports/
    ├── toshiba-tec.md
    ├── freee.md
    ├── pos-vendors.md
    ├── qrcode.md
    ├── e-bookkeeping.md
    ├── hitachi.md
    ├── citation-network.md
    └── prior-art-non-patent.md
```

---

## 作業手順

1. `reports/` → `legacy/` にリネーム
2. `claims/` ディレクトリを作成
3. `patent-list.md` を作成（特許番号一覧）
   - 既知の特許 + Airレジ/スマレジ等の未調査分もWebSearchで収集
4. 各特許の請求項ドキュメントを作成（Google Patents WebFetch）
5. 構成要件分析・侵害判定を追記
6. サマリドキュメントを更新

---

## 調査対象（既知）

### 登録特許

| 特許番号 | 権利者 | 有効期限 | リスク |
|---------|--------|---------|--------|
| JP6598936B2 | 東芝テック | 2034/09/05 | ハイライト表示 |
| JP6618585B2 | 東芝テック | 2033/09/06 | 返品連動 |
| JP5503795B1 | freee | 2033/03/18 | キーワード対応テーブル |

### 後続出願（要調査）

| 公報番号 | 権利者 | 備考 |
|---------|--------|------|
| JP2021080807A | 東芝テック | 6598936の後続出願 |
| JP2022167384A | 東芝テック | 6598936の後続出願 |
| JP2023136258A | 東芝テック | 6598936の後続出願 |
| JP2014182787A | freee | 5503795の関連出願 |

### 未調査（ステップ1で収集）

| 出願人 | 対象 | 方法 |
|--------|------|------|
| リクルート（Airレジ） | 電子レシート関連 | Google Patents / WebSearch |
| スマレジ | POS・レシート関連 | Google Patents / WebSearch |
| Square/Block | 米国特許 | Google Patents |
| NEC | POS関連 | Google Patents |
| 富士通 | POS関連 | Google Patents |

---

## 調査ツール

| ツール | 用途 | Claudeで実行可能 |
|--------|------|-----------------|
| Google Patents (WebFetch) | 請求項全文取得、メタ情報、関連出願 | ✅ |
| WebSearch | 特許番号の発見、ニュース | ✅ |
| J-PlatPat | 年金納付状況、審査書類 | ❌ オーナー対応 |

---

## 完了済み作業（前セッション）

- ✅ ディレクトリ構成整理（fto/ と ip-strategy/ に分離）
- ✅ CPM方式の認識修正（東芝テック特許はQRフローと無関係）
- ✅ Google Patentsで主要3特許の詳細情報取得
- ✅ ip-strategy/invention-candidates.md 作成（発明候補5件）
- ✅ README.md、CLAUDE.md更新

---

## Context

### ビジネスアイデアの概要（侵害判定に必要）

- QRコードで店舗-利用者を連携
- 電子領収書（レシートではない）を発行
- 店舗発行時点で勘定科目を自動付与
- 店舗・利用者双方で電帳法対応保管
- ワンタイムトークンによる認証
- POSベンダーへのAPI提供

### 回避必須の機能（現時点の認識）

| 機能 | 関連特許 | 有効期限 |
|------|---------|---------|
| ハイライト表示 | 東芝テック 6598936 | 2034/09/05 |
| 返品連動自動訂正 | 東芝テック 6618585 | 2033/09/06 |
| キーワード対応テーブル勘定科目判定 | freee 5503795 | 2033/03/18 |

### 発明候補（IP戦略側）

| # | 発明候補 | 推奨度 |
|---|---------|--------|
| A | 経費精算特化電子領収書発行システム | ★★★★★ |
| B | 店舗発行時点での勘定科目自動付与 | ★★★★★ |
| C | 店舗・利用者双方の電帳法対応保管 | ★★★★☆ |

---

## Reference Files

- `patents/README.md` - エントリーポイント
- `patents/fto/README.md` - FTO調査の概要・方法論
- `patents/fto/summary.md` - 調査結果サマリ（ステップ6で更新）
- `patents/fto/avoidance-checklist.md` - 回避チェックリスト
- `patents/fto/expiry-timeline.md` - 有効期限一覧
- `patents/ip-strategy/invention-candidates.md` - 発明候補詳細
- `CLAUDE.md` - プロジェクト全体のガイド
- `business/receipt-system-idea.md` - ビジネスアイデア（侵害判定の入力）

## External Sources

- [Google Patents JP6598936B2](https://patents.google.com/patent/JP6598936B2/ja)
- [Google Patents JP6618585B2](https://patents.google.com/patent/JP6618585B2/ja)
- [Google Patents JP5503795B1](https://patents.google.com/patent/JP5503795B1/ja)
