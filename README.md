# BacklogのWikiページを一度に複数作成できるpythonスクリプト

## 概要
- 複数のWikiページを一度に作成できる
- タグや階層も一度に作成できる
- タグや階層を一括登録したいときに使える
- プロジェクトは違うけど同じようなWiki構成にしたい場合に使える
- ドキュメントをWiki納品する場合、ドキュメント一覧をテンプレとして作っておいて一括でインポートすると楽

## 必要な環境
- python3の実行環境(ローカルでもクラウドでもOK)

## 使い方
### WikiページのCSV作成

CSVサンプル
```
name,content
タイトル01,テスト
[タグA][タグB]タイトル02,テスト
[タグA][タグB][タグC]タイトル03/子タイトル01,テスト
```

- 1行目はヘッダー
- 1行1Wikiページ
- Wikiタイトル,本文(カンマで区切る)
- [タグ]や/(階層)をつけておくと楽


### スクリプト内の自分で変更する箇所

APIKey:Backlogへログイン > 個人設定　> API でAPIキーを作成その文字列を<APIKey>へ入力
projectID:Backlogのプロジェクト > プロジェクト設定 をクリックすると表示されるURLのproject.idの値を入力
spaceID:契約しているBacklogのURLのサブドメイン名のところ(例 mongamae.backlog.jp -> mongamaeがspaceID)
csv filename:CSVファイル名
