# Session Snapshot: 特許調査

**Date:** 2026-02-04
**Topic:** 電子領収書発行システムの特許調査

---

## Current Task

QR Shop Receipt Systemのビジネスアイデアに関連する特許の網羅的調査を実施中。8つの調査領域をサブエージェントで並列実行したが、一部が途中停止する問題が発生。順次実行に切り替えて調査を継続。

---

## Files Modified / Created

### ディレクトリ再編成
- `patents/` - 特許調査用ディレクトリ（新規）
- `business/` - ビジネスプラン用ディレクトリ（新規）
- `docs/` - 技術ドキュメント用（既存を整理）

### 作成した調査関連ファイル
- `patents/CLAUDE.md` - 特許調査のガイドライン
- `patents/patent-investigation-plan.md` - 調査計画書

### 生成されたレポート（6件完了）
| ファイル | 内容 | 状態 |
|----------|------|------|
| `patents/report-freee.md` | freee特許調査 | ✅ 完了 |
| `patents/report-pos-vendors.md` | POSレジベンダー調査 | ✅ 完了 |
| `patents/report-qrcode.md` | QRコード認証・決済調査 | ✅ 完了 |
| `patents/report-citation-network.md` | 引用特許ネットワーク | ✅ 完了 |
| `patents/report-toshiba-tec.md` | 東芝テック特許調査 | ✅ 完了 |
| `patents/report-e-bookkeeping.md` | 電子帳簿保存法関連 | ✅ 完了 |

### 未完了のレポート（2件）
| ファイル | 内容 | 状態 |
|----------|------|------|
| `patents/report-hitachi.md` | 日立グループ特許 | ❌ 未完了 |
| `patents/report-prior-art-non-patent.md` | 公知例（特許DB以外） | ❌ 未完了 |

---

## Key Decisions

1. **ディレクトリ構成**: `patents/`, `business/`, `docs/` に分離
2. **調査方針**:
   - 特許有効期限の確認
   - 請求項解析と該当性判定
   - 引用特許の芋づる式調査
   - 公知例（特許DB以外）の収集
3. **調査対象出願人**: 東芝テック、freee、リクルート、スマレジ、日立グループ等

---

## Key Findings (これまでの調査結果)

### 高リスク特許
1. **東芝テック 特許6598936** (有効期限: 2034/09/05)
   - フラグによる表示態様変更機能
   - **回避策**: ハイライト表示機能を実装しない

2. **東芝テック 特許6618585** (有効期限: 2033/09/06)
   - 返品処理時の訂正電子レシート
   - **回避策**: 返品連動機能を実装しない

3. **freee 特許5503795**
   - キーワード対応テーブルによる勘定科目自動分類
   - **回避策**: 勘定科目自動判定は非実装、または機械学習方式

### 安全な実装
- 電子帳簿保存法対応（タイムスタンプ、訂正削除履歴）: 低リスク
- QRコード基本技術: 特許切れ（デンソーウェーブ）
- RFC3161準拠タイムスタンプ: オープン技術

---

## Next Steps

1. **残り2件の調査を完了**
   - 日立グループ特許調査
   - 公知例調査（特許DB以外）

2. **調査結果の統合**
   - `patent-landscape-summary.md` を作成
   - `implementation-avoidance.md` を作成（回避すべき実装一覧）
   - `patent-expiry-list.md` を作成（有効期限一覧）

3. **CLAUDE.md の更新**
   - 調査結果を反映して Patent Constraints セクションを更新

---

## Context

### プロジェクト概要
- **QR Shop Receipt System**: 電子領収書発行システム（B2B2C SaaS）
- **コア機能**: 店舗QRコード→利用者QRコード→電子領収書発行
- **差別化**: OCR不要（100%正確）、経費精算特化、電子帳簿保存法対応

### 技術スタック（予定）
- Backend: Rust + Axum
- Database: PostgreSQL
- Auth: OAuth2 / WebAuthn

### サブエージェント停止問題
並列実行したサブエージェントが途中で停止する現象が複数回発生。原因不明。順次実行に切り替えることで対処。

---

## Resume Commands

```bash
# 日立グループ特許調査
# 公知例調査（特許DB以外）
# を順次実行して完了させる

# その後、調査結果を統合してサマリーを作成
```
