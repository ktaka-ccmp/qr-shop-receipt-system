# 電子レシート・電子領収書・QRコード認証決済に関する公知例調査レポート

**調査日**: 2026年2月5日
**目的**: 特許データベース以外の公知例（学術論文、技術記事、製品、オープンソース等）の調査

---

## 1. 概要（公知例調査の目的と意義）

### 1.1 調査の目的

本調査は、電子レシート、電子領収書、QRコード認証決済に関する技術について、特許文献以外の公知例を収集することを目的とする。これらの公知例は以下の用途に活用できる：

1. **特許無効化の証拠**: 既存特許の新規性・進歩性を否定する先行技術として
2. **自由実施の確認**: 計画している技術が既に公知であることの証明
3. **技術動向の把握**: 業界標準や一般的な実装手法の理解
4. **設計回避の参考**: 特許侵害リスクを避けつつ同等機能を実現する方法の検討

### 1.2 公知例の法的意義

日本の特許法において、特許の無効理由として「出願前に公然知られた発明」「出願前に頒布された刊行物に記載された発明」「出願前に電気通信回線を通じて公衆に利用可能となった発明」が挙げられる（特許法第29条第1項）。

学術論文、技術ブログ、製品マニュアル、オープンソースコードは、発行日・公開日が明確であれば、特許出願日より前の先行技術として活用可能である。

---

## 2. 学術論文・研究

### 2.1 日本国内の研究（J-STAGE等）

#### 電子レシートを利用した購買データプラットホーム

- **著者**: 小野賢司、金田昌之、荒井康博、南部和哉
- **掲載**: 電子情報通信学会 通信ソサイエティマガジン, Vol.16, No.2 (2022)
- **URL**: https://www.jstage.jst.go.jp/article/bplus/16/2/16_131/_article/-char/ja/
- **概要**: 電子レシートを活用した購買データプラットフォームの構築に関する研究

#### POSデータ関連研究

- **タイトル**: POSデータに基づく欠品時の顧客行動を考慮した小売店舗の購買シミュレーション
- **掲載**: 人工知能学会論文誌 (J-STAGE)
- **URL**: https://www.jstage.jst.go.jp/article/tjsai/advpub/0/advpub_F-F13/_article/-char/ja/
- **概要**: POSデータを用いた顧客行動モデリングと購買シミュレーション

#### ID-POSデータ解析研究

- **タイトル**: ID-POSデータ解析に基づくネットチラシのプロモーション効果に関する研究
- **掲載**: J-STAGE
- **URL**: https://www.jstage.jst.go.jp/article/jbhmk/49/1/49_3/_article/-char/ja/
- **概要**: 隠れマルコフモデルとベイズ階層モデルを用いた購買記録分析

### 2.2 国際的な研究（IEEE、ResearchGate等）

#### QRコードによる二要素認証

- **タイトル**: QR code based two-factor authentication to verify paper-based documents
- **URL**: https://www.researchgate.net/publication/343368029
- **概要**: 紙文書の真正性検証のためのQRコード二要素認証システム。証明書や領収書の偽造防止に応用可能。

#### QRコードの偽造防止技術

- **タイトル**: Innovative QR Code System for Tamper-Proof Generation and Fraud-Resistant Verification
- **掲載**: PMC (NIH)
- **URL**: https://pmc.ncbi.nlm.nih.gov/articles/PMC12252379/
- **概要**: デジタル透かし技術を用いた改ざん防止QRコード生成・検証システム

#### テクスチャ隠蔽型偽造防止QRコード

- **タイトル**: A Texture-Hidden Anti-Counterfeiting QR Code and Authentication Method
- **URL**: https://www.researchgate.net/publication/367070410
- **概要**: ランダムテクスチャパターンを組み合わせた複製防止機能付きQRコード

#### デジタル署名とQRコード

- **タイトル**: Academic Document Authentication using Elliptic Curve Digital Signature Algorithm and QR Code
- **URL**: https://www.researchgate.net/publication/364168758
- **概要**: 楕円曲線デジタル署名をQRコードに埋め込む文書認証方式

### 2.3 公知例としての意義

これらの学術論文は、QRコードを用いた認証・ワンタイムトークン・文書真正性検証の技術が学術的に広く研究されていることを示す。特に2017年以前の論文は、同時期以降に出願された関連特許の進歩性を否定する根拠となりうる。

---

## 3. 技術記事・ブログ

### 3.1 QRコード決済の技術解説

#### QRコード決済の仕組み解説

- **タイトル**: QRコード決済の仕組みを徹底解説
- **出典**: CIO Japan
- **URL**: https://www.cio.com/article/4076472/
- **公開時期**: 2018年頃
- **内容**:
  - QRコード決済における認証の仕組み
  - 動的QRコードの有効期限（TTL）設定
  - ワンタイム参照番号の使用
  - 電子署名付きトークンの組み込み

#### ワンタイムQR認証

- **タイトル**: 一度しか使えないQRコードで認証をさらに簡単＆セキュアに
- **出典**: サイバーセキュリティ.com
- **URL**: https://cybersecurity-jp.com/interview/51040
- **内容**:
  - 一度のみ使用可能、60秒など決まった時間のみ有効なトークン生成
  - 2回目以降の読み込みはエラーとなる仕組み
  - 30秒ごとに切り替わるワンタイムQRコード

### 3.2 電子レシート関連記事

#### 経産省実証実験報告

- **タイトル**: 標準仕様策定が進む電子レシート ～ 経産省・NEDO実証実験報告
- **出典**: 東京エレクトロンデバイス
- **URL**: https://esg.teldevice.co.jp/iot/blog/017/
- **公開**: 2018年
- **内容**:
  - 2018年2月、東京都町田市での実証実験
  - 27店舗、約2,700人の顧客が参加
  - 標準フォーマットとAPIの策定

#### レシート革命

- **タイトル**: レシート革命が始まった
- **出典**: 株探ニュース
- **URL**: https://kabutan.jp/news/marketnews/?b=n201802100303
- **公開**: 2018年2月
- **内容**: 電子レシートの普及動向と技術的背景

### 3.3 公知例としての意義

これらの技術記事は、QRコード認証やワンタイムトークンの具体的な実装方法が一般に公開されていたことを示す。特に2018年の経産省実証実験の詳細な技術報告は、当時の技術水準を示す重要な公知例となる。

---

## 4. 既存サービス・製品

### 4.1 日本国内の電子レシートサービス

#### スマートレシート（東芝テック）

- **サービス開始**: 2014年10月31日
- **URL**: https://www.smartreceipt.jp/
- **プレスリリース**: https://www.toshibatec.co.jp/release/20141031_01.html
- **技術的特徴**:
  - 会計時にレシートを電子化
  - 電子レシートセンターでデータ管理
  - スマートフォンで購入履歴をいつでも確認
- **実績**:
  - 2024年度：約7,500万枚の電子レシート発行
  - 会員数：250万人突破（2025年4月）
  - 稼働店舗：543社・17,315店
- **公知例としての重要性**: 2014年のサービス開始は、電子レシートの基本的な仕組み（QRコード表示、スマホ読取、クラウド保存）が公知であったことを示す

#### レシートローラー

- **サービス概要**: ヘッドレス電子レシートサービス
- **URL**: https://receiptroller.com/
- **API**: https://api.receiptroller.com
- **GitHub**: https://github.com/Receipt-Roller/RECEIPTROLLER-Dev.
- **技術的特徴**:
  - POSからの電子レシート発行API
  - LINE、メール、SMS等の複数チャネル対応
  - Square連携機能

### 4.2 POSレジサービスの電子レシート機能

#### Airレジ（リクルート）

- **電子レシート機能発表**: 2022年11月8日
- **URL**: https://faq.airregi.jp/hc/ja/articles/11944716243481
- **特徴**:
  - QRコード表示による電子レシート発行
  - メールでの電子レシート送付
  - 店舗SNSリンクの表示

#### スマレジ

- **API**: https://www1.smaregi.dev/apidoc/
- **特徴**:
  - プラットフォームAPI提供
  - レジ端末、取引、精算処理等の機能

#### Square

- **電子レシート機能**: https://squareup.com/help/jp/ja/article/5070
- **API**: ReceiptOptions Object
- **特徴**:
  - メール・SMSでの電子レシート送信
  - Payments API経由でのreceipt_url取得

### 4.3 QRコード決済サービス

#### PayPay

- **決済方式**:
  - ユーザースキャン方式：店舗QRコードをユーザーが読み取り
  - ストアスキャン方式：ユーザーのバーコードを店舗がスキャン
- **URL**: https://paypay.ne.jp/
- **公知例としての意義**: 2018年のサービス開始以降、QRコード決済の標準的な実装として広く知られる

#### LINE Pay

- **QRコード統一**: PayPayのQRコードとの統一（2022年）
- **URL**: https://www.watch.impress.co.jp/docs/news/1420252.html

### 4.4 海外のデジタルレシートサービス

#### ReceiptHero（フィンランド）

- **設立**: 2018年後半
- **資金調達**: 200万ユーロ（シード、2020年12月）
- **URL**: https://getreceipthero.com/
- **提携**: Nordea、SEB（銀行）、Visa、Mastercard
- **特徴**:
  - 銀行・マーチャント向けオープンエコシステム
  - POSシステムとの統合
  - 主要カードプロバイダー対応

#### Flux（英国）- サービス終了

- **設立**: 2016年
- **サービス終了**: 2022年10月
- **資金調達**: 合計910万ドル
- **URL**: https://www.fintechfutures.com/2022/10/digital-receipts-start-up-flux-closing-down/
- **公知例としての意義**: 2016年からの運営実績は、デジタルレシート管理インフラの技術が早期に実用化されていたことを示す

#### fiskaly（ドイツ）

- **Google Wallet連携**: デジタルレシートのGoogle Wallet統合
- **URL**: https://www.fiskaly.com/blog/digital-receipt-by-fiskaly-integrated-into-google-wallet

### 4.5 ロシアの電子レシートシステム（OFD）

- **施行日**: 2017年7月1日
- **概要**: リアルタイム税務報告のための電子レシート義務化
- **URL**: https://sovos.com/blog/2017/08/30/iot-real-time-tax-controls-for-russian-b2c-transactions/
- **技術的特徴**:
  - 認定キャッシュデスク（CCD）によるIoTデバイス
  - 財務データオペレーター（OFD）経由のリアルタイム報告
  - QRコード付きレシートによる消費者向け検証機能
  - 1日7,000万件のB2C取引を処理
- **公知例としての意義**: 国家レベルでの電子レシート・QRコード検証システムの大規模実装例

---

## 5. オープンソース実装

### 5.1 ReceiptLine（OFSC）

- **GitHub**: https://github.com/receiptline/receiptline
- **npm**: https://www.npmjs.com/package/receiptline
- **仕様**: OFSC ReceiptLine Specification
- **管理**: Open Foodservice System Consortium (http://www.ofsc.or.jp/)
- **特徴**:
  - レシート記述言語（Receipt Markdown）
  - 紙幅に依存しないテキストデータ形式
  - レシートプリンタ出力と電子レシート表示の両対応
  - Epson TM、Seiko RP、Star MC等のプリンタ対応
- **関連プロジェクト**:
  - receiptio: レシート印刷アプリケーション
  - receiptjs: JavaScriptライブラリ
  - receipt-markdown: VS Code拡張

### 5.2 EMV QRコード実装

- **GitHub**: https://github.com/mvallim/emv-qrcode
- **言語**: Java
- **機能**: EMV QRコード生成・解析（MPM、CPM対応）
- **仕様準拠**: EMVCo QR Code Specification

### 5.3 レシートOCR・スキャナー

#### BudgetLens

- **GitHub**: https://github.com/1oannis/budget-lens
- **特徴**: オープンソースのレシートスキャナー・経費トラッカー（セルフホスト対応）

#### Receipt Scanner for Laravel

- **GitHub**: https://github.com/HelgeSverre/receipt-scanner
- **特徴**: AI（OpenAI）を活用したレシートデータ抽出

### 5.4 公知例としての意義

これらのオープンソースプロジェクトは、電子レシートの生成・表示・解析に関する具体的な実装が公開されていることを示す。特にReceiptLineのOFSC仕様は、業界標準としての位置づけを持つ。コミット履歴から公開日を特定でき、先行技術の証拠として有効である。

---

## 6. 標準化・規格

### 6.1 日本国内の標準・規格

#### 経済産業省 標準電子レシートフォーマット仕様書

- **公開日**: 2018年5月14日
- **策定経緯**: 2018年2月の町田市実証実験を基に策定
- **URL**: https://www.meti.go.jp/press/2018/01/20190115005/20190115005.html
- **技術仕様**:
  - JSON形式採用
  - レシート印字項目の網羅的定義
  - 同一意味項目の同一タグへの格納
  - 利用方法の柔軟性確保
- **公知例としての重要性**: 政府機関による標準仕様の公開は、当該技術の公知性を強く裏付ける

#### JPQR（統一QRコード規格）

- **策定**: 2019年3月29日
- **策定者**: キャッシュレス推進協議会
- **URL**: https://paymentsjapan.or.jp/wp-content/uploads/2022/02/MPM_Guideline_2.0.pdf
- **仕様内容**:
  - 利用者提示型（CPM）統一技術仕様
  - 店舗提示型（MPM）統一技術仕様
  - 静的QRコード、動的QRコード、請求書払い
- **参加事業者**: PayPay、d払い、au PAY等11社

#### 電子帳簿保存法

- **改正**: 2022年1月
- **URL**: https://www.nta.go.jp/law/joho-zeikaishaku/sonota/jirei/tokusetsu/index.htm
- **主要要件**:
  - 電子取引データの電子保存義務化
  - スキャナ保存のタイムスタンプ要件緩和（3日→約2ヶ月7日以内）
  - 訂正削除履歴の保存要件

#### 電子インボイス（Peppol / JP PINT）

- **概要**: 国際標準Peppolに基づく日本版デジタルインボイス仕様
- **策定者**: デジタル庁
- **URL**: https://www.freee.co.jp/kb/kb-invoice/peppol/
- **特徴**:
  - 構造化されたデータ形式
  - 国際的な相互運用性
  - 日本の税制度・商習慣への対応

### 6.2 国際標準・規格

#### EMVCo QR Code Specification

- **策定者**: EMVCo
- **URL**: https://www.emvco.com/emv-technologies/qr-codes/
- **仕様書**: EMV QR Code Specification for Payment Systems (EMV QRCPS)
- **内容**:
  - Consumer-Presented Mode (CPM): 消費者がQRコード表示
  - Merchant-Presented Mode (MPM): 店舗がQRコード表示
- **採用国**: シンガポール、南アフリカ等で国家標準として採用
- **特徴**:
  - 複数の国内・国際決済オプション対応
  - カードベース・アカウントベース両対応
  - ロイヤリティフリーで公開

#### ISO 14533（長期署名）

- **タイトル**: Processes, data elements and documents in commerce, industry and administration – Long term signature profiles
- **URL**: https://www.iso.org/standard/79129.html
- **目的**: 電子文書の長期間真正性保証
- **構成**:
  - Part 1: CAdES（CMS Advanced Electronic Signatures）
  - Part 2: XAdES（XML Advanced Electronic Signatures）
- **電子レシートへの適用**: 電子領収書の長期保存・真正性検証に活用可能

### 6.3 公知例としての意義

これらの標準・規格文書は、以下の点で特許無効化の重要な証拠となりうる：

1. **公開日の明確性**: 政府機関・標準化団体による公式発行日が記録されている
2. **技術的詳細**: 具体的な実装仕様が詳細に記載されている
3. **広範な周知性**: 業界全体に周知されている標準仕様である
4. **継続的な公開**: Webサイト等で継続的に公開されている

---

## 7. 公知例の活用方法（特許無効化への活用可能性）

### 7.1 特許無効化の基本的な考え方

特許を無効化するためには、以下のいずれかを証明する必要がある：

1. **新規性の欠如**: 出願日前に同一の発明が公知であった
2. **進歩性の欠如**: 出願日前の公知技術から容易に想到できた

### 7.2 本調査で発見された公知例の活用可能性

#### 電子レシートの基本概念（2014年以前の公知例）

| 公知例 | 公開日 | 証明できる技術 |
|--------|--------|----------------|
| スマートレシート サービス開始 | 2014年10月31日 | 電子レシートのクラウド保存、スマホ閲覧 |
| Flux（英国）設立 | 2016年 | デジタルレシート管理インフラ |

#### QRコード認証・ワンタイムトークン（2017年以前の公知例）

| 公知例 | 公開日 | 証明できる技術 |
|--------|--------|----------------|
| ロシアOFDシステム | 2017年7月1日 | QRコード付き電子レシート、リアルタイム検証 |
| QRコード二要素認証論文 | 2020年以前 | QRコードによる文書真正性検証 |

#### 標準仕様・API（2018年以降の公知例）

| 公知例 | 公開日 | 証明できる技術 |
|--------|--------|----------------|
| 経産省標準フォーマット | 2018年5月14日 | 電子レシートのJSON形式、標準項目定義 |
| JPQR仕様 | 2019年3月29日 | 統一QRコード決済仕様 |
| EMVCo QR Spec | 2017年以降 | QRコード決済の国際標準 |

### 7.3 具体的な無効化シナリオ

#### シナリオ1: 電子レシートの基本機能に関する特許

**対象**: 電子レシートをスマートフォンに送信・保存する特許
**無効化根拠**:
- スマートレシート（2014年10月）の公開
- 経産省標準フォーマット（2018年5月）の公開

#### シナリオ2: QRコードによるワンタイム認証に関する特許

**対象**: QRコードにワンタイムトークンを埋め込む認証方式
**無効化根拠**:
- QRコード二要素認証に関する学術論文
- ロシアOFDシステム（2017年7月）の実装
- EMVCo QR Code Specification

#### シナリオ3: 電子領収書と会計ソフト連携に関する特許

**対象**: 電子領収書を会計ソフトにAPI連携する特許
**無効化根拠**:
- freee/MoneyForward APIドキュメント
- レシートローラー API仕様
- 経産省電子レシートAPI仕様（2018年5月）

### 7.4 証拠保全の方法

1. **Wayback Machine**: Internet Archive（https://web.archive.org/）でのスナップショット
2. **学術論文**: DOI付き論文のアーカイブ
3. **GitHub**: コミット履歴による公開日の証明
4. **プレスリリース**: 企業・政府機関の公式発表
5. **公的文書**: 官報、政府広報オンライン

---

## 8. 結論

### 8.1 調査結果のまとめ

本調査により、電子レシート・電子領収書・QRコード認証決済に関する以下の公知例を発見した：

| カテゴリ | 件数 | 主要な公知例 |
|----------|------|--------------|
| 学術論文 | 6件+ | J-STAGE論文、IEEE/ResearchGate論文 |
| 技術記事 | 5件+ | CIO Japan、サイバーセキュリティ.com等 |
| 既存サービス | 10件+ | スマートレシート、ReceiptHero、Flux等 |
| オープンソース | 5件+ | ReceiptLine、emv-qrcode等 |
| 標準・規格 | 6件+ | 経産省標準、JPQR、EMVCo、Peppol等 |

### 8.2 QRショップレシートシステムへの示唆

本プロジェクト「QR Shop Receipt System」の開発において、以下の点に留意すべきである：

1. **基本機能は公知**: 電子レシートの発行・保存・閲覧という基本機能は広く公知であり、これらの機能自体に対する特許リスクは低い

2. **QRコード認証も公知**: ワンタイムトークンを用いたQRコード認証は、学術論文・製品・標準仕様で広く公開されている

3. **差別化ポイント**: 以下の点は相対的に公知例が少ない可能性がある：
   - 電子帳簿保存法対応の訂正削除履歴管理
   - 印紙税削減を目的とした電子領収書発行
   - B2B2C SaaSとしてのビジネスモデル

4. **特許回避設計**: CLAUDE.mdに記載の通り、以下は特許侵害リスクがあるため回避すべき：
   - 特定項目のハイライト表示（東芝テック特許6598936）
   - キーワードマッチング表による自動勘定科目分類（freee特許5503795）

### 8.3 今後の調査推奨事項

1. **Internet Archive調査**: 2014年前後のスマートレシート等のサービス画面のスナップショット取得
2. **特許庁意見書・審査経過**: 類似特許の審査過程で引用された先行技術の確認
3. **業界カンファレンス資料**: CEATEC、リテールテック等の展示資料
4. **弁理士・弁護士との協議**: 具体的な特許無効化戦略の検討

---

## 参考文献・URL一覧

### 学術論文
- [電子レシートを利用した購買データプラットホーム](https://www.jstage.jst.go.jp/article/bplus/16/2/16_131/_article/-char/ja/)
- [QR code based two-factor authentication](https://www.researchgate.net/publication/343368029)
- [Innovative QR Code System for Tamper-Proof Generation](https://pmc.ncbi.nlm.nih.gov/articles/PMC12252379/)

### 技術記事
- [QRコード決済の仕組み - CIO](https://www.cio.com/article/4076472/)
- [ワンタイムQR認証](https://cybersecurity-jp.com/interview/51040)
- [経産省・NEDO実証実験報告](https://esg.teldevice.co.jp/iot/blog/017/)

### 既存サービス
- [スマートレシート](https://www.smartreceipt.jp/)
- [レシートローラー](https://receiptroller.com/)
- [ReceiptHero](https://getreceipthero.com/)
- [Square 電子レシート](https://squareup.com/help/jp/ja/article/5070)

### オープンソース
- [ReceiptLine - GitHub](https://github.com/receiptline/receiptline)
- [EMV QRCode - GitHub](https://github.com/mvallim/emv-qrcode)

### 標準・規格
- [経産省 標準購買履歴データフォーマット](https://www.meti.go.jp/press/2018/01/20190115005/20190115005.html)
- [JPQR 統一技術仕様ガイドライン](https://paymentsjapan.or.jp/wp-content/uploads/2022/02/MPM_Guideline_2.0.pdf)
- [EMVCo QR Codes](https://www.emvco.com/emv-technologies/qr-codes/)
- [電子帳簿保存法特設サイト](https://www.nta.go.jp/law/joho-zeikaishaku/sonota/jirei/tokusetsu/index.htm)

---

*本レポートは2026年2月5日時点の公開情報に基づいて作成されています。*
