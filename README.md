# Doc Management Test

VSCode を使った **Markdown ドキュメント管理手法の検証** を目的としたリポジトリです。

## 概要

Markdown ファイルを中心としたドキュメント群を Git で管理しながら、以下の検証を行っているリポジトリです。

- VSCode + Git による Markdown ドキュメント管理の検証
- Claude Code との連携による文書作成フローの検証
- draw.io で作成した SVG 画像および画像内リンクの対応（リンクの確認には docsify 経由が必要。Cloudflare 公開 URL またはローカル環境で確認可能）
- Edit CSV 拡張機能による CSV 編集と grid.js を使ったブラウザ上での表表示

## ファイル構成

| ファイル | 内容 |
|---------|------|
| [docs/環境構築メモ.md](docs/環境構築メモ.md) | VSCode のインストール・拡張機能・設定などの構築手順メモ |
| [docs/画像張り込みテスト.md](docs/画像張り込みテスト.md) | Markdown へのクリップボード画像貼り付け手順の検証 |
| [docs/フロー図/フロー図1.md](docs/フロー図/フロー図1.md) | draw.io で作成したフロー図のサンプル（リンク付きノードあり） |
| [docs/フロー図/フロー図2.md](docs/フロー図/フロー図2.md) | draw.io で作成したフロー図のサンプル |
| [docs/更新履歴.md](docs/更新履歴.md) | 日単位の変更履歴 |
| [docs/四字熟語.md](docs/四字熟語.md) | grid.js テーブル表示の検証ページ（CSV を表として表示） |
| [index.html](index.html) | docsify 設定ファイル（SVG リンク対応・grid.js CSV テーブル対応プラグイン含む） |
| [_sidebar.md](_sidebar.md) | docsify サイドバー定義 |
| [images/](images/) | クリップボードから貼り付けた画像の格納フォルダ |
| [dio_images/](dio_images/) | draw.io で作成した SVG ファイルの格納フォルダ |
| [data/](data/) | CSV ファイルの格納フォルダ（Edit CSV で編集） |

## ドキュメント閲覧

### 公開 URL（Cloudflare）

GitHub 経由で Cloudflare に公開しており、以下の URL からブラウザで閲覧できる。

https://doctest.wawonpapa.workers.dev/#/

### ローカル環境での確認

ローカルで確認する場合は、VSCode のターミナルでリポジトリのルートに移動し、以下のコマンドを実行する。

```bash
python -m http.server 5000
```

起動後、ブラウザで `http://localhost:5000` を開く。

## TODO

- draw.io の共通テンプレートの作成・共有方法の確立（パス指定の改善とも絡む可能性あり）
- draw.io でフロー内にリンクを埋め込む際・フローを md に埋め込む際のパス指定が煩雑なため、何らかの方法で改善したい
- docsify 表示用サイドバーツリーの自動生成（フォルダ階層や命名ルールを元に自動生成する仕組みを検討）
- 上記と並行して、左ツリーの階層化まわりのテスト（md 内の見出しはツリー上には不要な可能性がある）
- （できれば）docsify でキャッシュが残りやすい問題の解決（現状はブラウザのシークレットモードでキャッシュ削除で対応しているが手間）
- docsify 用ローカルサーバの起動を自動化・簡略化し、都度ターミナルから Python コマンドを叩かなくて済むようにする

## 注意事項

- このリポジトリはテスト用途のため、内容は随時変更されます。
- 本番環境のドキュメントは含まれていません。
- draw.io SVG 内のリンクは VSCode・GitHub のプレビューでは動作しない。docsify 経由で確認すること。
