# 特許関連ドキュメント

**最終更新:** 2026年2月5日

---

## ディレクトリ構成

```
patents/
├── README.md              # このファイル（エントリーポイント）
│
├── fto/                   # Freedom to Operate（侵害回避）
│   ├── README.md          # FTO調査の概要
│   ├── summary.md         # 調査結果サマリー
│   ├── avoidance-checklist.md  # 回避チェックリスト
│   ├── expiry-timeline.md # 有効期限一覧
│   └── reports/           # 詳細調査レポート（8件）
│
├── ip-strategy/           # 自社IP戦略（権利化）
│   ├── README.md          # IP戦略の概要
│   ├── invention-candidates.md  # 発明候補一覧
│   └── prior-art-searches/      # 新規性調査（未着手）
│
└── archive/               # 過去の調査資料（参考用）
```

---

## 読み方ガイド

### 目的別

| 目的 | 参照先 |
|------|--------|
| **他社特許を侵害しないための確認** | [fto/README.md](fto/README.md) |
| **自社発明の特許出願検討** | [ip-strategy/README.md](ip-strategy/README.md) |

---

## FTO（Freedom to Operate）サマリー

### 回避必須の機能

| 機能 | 関連特許 | 有効期限 |
|------|---------|---------|
| ハイライト表示（色・背景変更） | 東芝テック 6598936 | 2034年頃* |
| 返品連動の自動訂正レシート | 東芝テック 6618585 | 2033年頃* |
| キーワード対応テーブルによる勘定科目自動判定 | freee 5503795 | 2033年頃 |

*有効期限はJ-PlatPatで要確認

### 安全に実装可能

- 電子領収書の発行・保存・配信
- QRコードによる店舗-利用者連携
- タイムスタンプ付与（RFC3161準拠）
- 訂正削除履歴管理
- PDF/CSVエクスポート

詳細: [fto/avoidance-checklist.md](fto/avoidance-checklist.md)

---

## IP戦略サマリー

### 発明候補

| # | 発明候補 | 推奨度 |
|---|---------|--------|
| **A** | 経費精算特化電子領収書発行システム | ★★★★★ |
| **B** | 店舗発行時点での勘定科目自動付与 | ★★★★★ |
| **C** | 店舗・利用者双方の電帳法対応保管 | ★★★★☆ |

### 最大の差別化ポイント

> **東芝テック スマートレシート FAQ:**
> 「領収書については電子化はされず、今まで通り紙で出力されます」

→ 本システム（電子**領収書**）はスマートレシート（電子**レシート**）と別市場

詳細: [ip-strategy/invention-candidates.md](ip-strategy/invention-candidates.md)

---

## 推奨アクション

### 開発者向け

1. [fto/avoidance-checklist.md](fto/avoidance-checklist.md) を確認
2. 実装禁止事項に該当しないことを確認してから開発

### 経営・法務向け

1. [fto/summary.md](fto/summary.md) でリスク概要を把握
2. [ip-strategy/README.md](ip-strategy/README.md) で出願計画を確認
3. 弁理士への相談を手配

---

## 注意事項

- 本調査はWeb検索ベースの予備調査です
- 正式な特許調査・鑑定は弁理士に依頼してください
- **出願検討中の発明内容を外部に公開しないでください**（新規性喪失）
