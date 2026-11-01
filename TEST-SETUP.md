# MJ STATS v2 テスト環境【TEST】

このファイルは、テスト公開専用の記録です。

本番サイトとは別オリジンで公開します。

テストURLは次のとおりです。

https://drkudou-mj-test.github.io/mahjong-score-app-test/

本番URLは次のとおりです。

https://drkudou-create.github.io/mahjong-score-app/

ホスト名が異なるため、localStorageは本番と共有されません。

保存キー mahjongMobileTarget.v3 は変更しません。

Netlifyは使用しません。

既存リポジトリのPages公開元は変更しません。

本番ブランチ main へのマージは行いません。

## 公開構成

- 公開元は Deploy from a branch です。
- ブランチは main、フォルダは / (root) です。
- ビルドコマンドはありません。
- 独自のActionsワークフローファイルは追加しません。
- GitHub Pages側の標準ビルド・デプロイ処理は使います。

## 公開するファイル【TEST】

ルートに置くファイルは、次のものだけです。

- index.html
- manifest.json
- app-icon.png
- app-icon-192.png
- app-icon-512.png
- apple-touch-icon.png
- Nyashi.ttf
- TEST-CHANGES.md
- TEST-SETUP.md
-.gitignore
- player-icons/icon-01.png 〜 icon-52.png

player-iconsの52枚は、既存リポジトリのルートにあった既存ファイルを
コピーしたものです。

生成や画像変更はしていません。

## 公開しないもの

次のものは、リポジトリに入れません。

- 実際のバックアップJSON
- 開発用ZIP
- archive-embedded-history/
- 個人の過去履歴アーカイブ
- 認証情報やアクセストークン

## コードの状態【TEST】

基準は「麻雀集計 v77 成績固定・詳細設定修正版」です。

タイトル末尾にが付いています。

自動取り込み7件は停止済みです。

- v112
- v115
- v117
- v120
- v121
- v122
- v123

起動時のlocalStorage読み取り例外で保存禁止にします。

復元前に現在のデータを読み取れなかった場合、復元を中止します。

保存キー・保存形式・計算・ウマ既定値・デザイン・アイコン・フォントは
変更していません。

ウマ既定値は [20,10,-10,-20] のままです。

バックアップの設定 [30,10,-10,-30] と混同して変更しません。

Service Workerの追加、プレイヤーアイコン52枚の生成、新機能、
大規模リファクタリングは行いません。

## 確認手順【TEST】

バックアップを読み込む前に、分離を確かめます。

1. テストURL【TEST】を開きます。
2. の表示と、既定の履歴3件だけであることを見ます。
3. 自動取り込みの表示が出ないことを見ます。
4. テスト環境だけでダミー1回戦を追加します。
5. 再読み込みでダミーが残ることを見ます。
6. 本番URLは開きません。
7. 分離を確認してから、指定されたバックアップのコピーだけを
テスト環境【TEST】で読み込みます。
