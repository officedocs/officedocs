# OfficeDocs

[English](README.md) · [Deutsch](README.de.md) · [Webサイト](https://officedocs.io)

OfficeDocsは、ドキュメント、表計算、プレゼンテーションなどを共同編集できるセルフホスト型のスイートです。このリポジトリにはリリース情報と導入手順を収録しています。アプリケーションのソースコードではなく、利用には製品ライセンスが適用されます。

## 評価を始める

1. [ダウンロードページ](https://officedocs.io/download)からamd64またはarm64のZIPを取得します。インストーラー、製品パッケージ、INSTALL.mdが含まれます。資料の閲覧とダウンロードにWebサイトへの登録は不要です。
2. [SHA256SUMS](SHA256SUMS)でハッシュ値を照合し、[クイックスタート](https://officedocs.io/ja/docs/deployment/getting-started/quick-start)に従います。
3. 同梱手順の対象はUbuntu 24.04 LTS、CPU 16コア、メモリ32GB、SSD 100GBの単一ノードでのオンライン導入です。インターネット接続が必要です。本番環境の処理容量を保証する数値ではありません。[システム要件](https://officedocs.io/ja/docs/deployment/system-requirements)で長期運用の容量計画も確認してください。
4. [support.global@shimo.im](mailto:support.global@shimo.im)へライセンスを申請します。5ユーザーまでは永続無料です。有料プランを含む条件は[料金ページ](https://officedocs.io/pricing)を参照してください。

インストーラーへのアクセスとライセンス申請には、現在の[導入手順](docs/INSTALL.md)を使用してください。この点では変更していないZIP内の手順より優先します。管理ポートは公開せず、認証情報の入力前にSSHトンネルを使用します。公開パッケージはオンラインAll-in-One用です。標準Kubernetes、高可用性、オフライン構成には、対応する配布物をサポートへ事前に確認してください。

製品リリースは`co1.8.20260830.3884-drive-release`、インストーラーは`v1.8.1-rc12-global`です。OfficeDocsは、ShimoDocsと同じ基盤製品を使用する独立した海外向けブランドです。承認された従来のパッケージを変更せず配布するため、技術的なファイル名や一部画面にはShimoDocsの名称が残ります。パッケージは[このリポジトリの公開リリース](https://github.com/officedocs/officedocs/releases/tag/co1.8.20260830.3884-drive-release)とダウンロードページから取得できます。チェックサムの一致はファイルの整合性を示すもので、実際の導入成功を保証しません。

[ドキュメント](https://officedocs.io/ja/docs) · [導入手順（英語）](docs/INSTALL.md) · [お問い合わせ](https://officedocs.io/contact-sales)

## リポジトリ内のドキュメント

[ドキュメント一覧](docs/ja/README.md) · [全目次](docs/ja/deployment/README.md) · [クイックスタート](docs/ja/deployment/getting-started/quick-start.md) · [システム要件](docs/ja/deployment/system-requirements.md)

導入、ミドルウェア、ライセンスとテナント管理、運用、トラブルシューティングを収録しています。[English](docs/README.md) · [Deutsch](docs/de/README.md)。
