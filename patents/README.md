# 特許調査ドキュメント

**最終更新:** 2026年2月5日

---

## 読み方ガイド

### まず読むべきドキュメント

| 順番 | ファイル | 内容 | 対象読者 |
|------|---------|------|---------|
| **1** | [summary.md](summary.md) | 調査結果の総合サマリー | 全員 |
| **2** | [avoidance-checklist.md](avoidance-checklist.md) | 実装禁止事項のチェックリスト | 開発者 |
| **3** | [expiry-timeline.md](expiry-timeline.md) | 特許有効期限一覧 | 経営・法務 |

### 詳細レポート（必要に応じて参照）

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

### アーカイブ（過去の調査資料）

[archive/](archive/) ディレクトリには、調査過程で作成された古いバージョンのドキュメントを保管しています。正式な参照先ではありませんが、調査の経緯を確認する際に参照してください。

---

## 調査結論サマリー

### 回避必須の機能（実装禁止）

| 機能 | 関連特許 | 有効期限 |
|------|---------|---------|
| ハイライト表示（色・背景変更） | 東芝テック 6598936 | 2034年頃 |
| 返品連動の自動訂正レシート | 東芝テック 6618585 | 2033年頃 |
| キーワード対応テーブルによる勘定科目自動判定 | freee 5503795 | 2033年頃 |

### 安全に実装可能な機能

- 電子領収書の発行・保存・配信
- QRコードによる店舗-利用者連携
- タイムスタンプ付与（RFC3161準拠）
- 訂正削除履歴管理
- PDF/CSVエクスポート
- 会計ソフト連携（勘定科目判定は会計ソフト側）

### 調査未完了（要追加調査）

- Airレジ/スマレジの特許（J-PlatPat詳細調査必要）
- Square/Blockの米国特許（USPTO調査必要）

---

## 重要な注意事項

### 有効期限について

本調査で記載している有効期限は**推定値**です。正確な有効期限はJ-PlatPatで確認してください。

特に、東芝テック特許6598936については：
- 出願日: 2018年7月5日
- 優先権日: 2014年6月9日（報告書記載の2034年はこれを基準にした可能性）
- 正確な有効期限は要確認

### 本調査の限界

1. Web検索ベースの予備調査であり、J-PlatPat等での網羅的検索は一部未実施
2. 法的助言ではありません。最終判断は弁理士・弁護士に相談してください
3. 特許情報は変更される可能性があります

---

## ディレクトリ構成

```
patents/
├── README.md              # このファイル（エントリーポイント）
├── summary.md             # 調査結果サマリー
├── avoidance-checklist.md # 回避チェックリスト
├── expiry-timeline.md     # 有効期限一覧
├── reports/               # 詳細調査レポート
│   ├── toshiba-tec.md
│   ├── freee.md
│   ├── pos-vendors.md
│   ├── qrcode.md
│   ├── e-bookkeeping.md
│   ├── hitachi.md
│   ├── citation-network.md
│   └── prior-art-non-patent.md
└── archive/               # 過去の調査資料（参考用）
    ├── patent-analysis-revised.md
    ├── patent-investigation-plan.md
    └── ...
```

---

## 更新履歴

| 日付 | 内容 |
|------|------|
| 2026-02-05 | ディレクトリ構成を整理、README.md作成 |
| 2026-02-04 | 8件の詳細調査レポート完成 |
| 2026-02-03 | 特許調査開始 |
