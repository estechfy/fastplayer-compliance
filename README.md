# FastPlayer LGPL対応ソース・再リンクキット

FastPlayerが同梱するFFmpeg・dav1dの対応ソース、ライセンス、同じ版の再リンクキットを公開する専用リポジトリです。

[版別の配布物](https://github.com/estechfy/fastplayer-compliance/releases)から、利用中のアプリのバージョンとビルド番号に一致する添付物を取得してください。過去の版の添付物は保管します。

## 添付物

- `FFmpeg-compliance.zip`: 同梱版と一致するFFmpeg/dav1dソース、configure設定、ビルド手順、ライセンス、SHA-256一覧。
- `FastPlayer-relink.zip`: FastPlayerのリンク用オブジェクト、同梱ライブラリ、資源、`relink.sh`、コンパイラ・SDK情報。
- `SHA256SUMS`: 公開添付物のSHA-256一覧。

FFmpegはLGPL v2.1以降、dav1dは同梱のBSDライセンスに従います。各ライセンス原文と著作権表示は添付物内で確認してください。FastPlayer独自部分のソースコードを公開するリポジトリではありません。

## 自分のライブラリで再リンクする

Macにキット記載のXcodeツールチェーンを用意し、再リンクキットを展開します。同じmajor ABIのFFmpeg動的ライブラリを用意して、次を実行してください。

```sh
bash relink.sh /absolute/path/to/modified-ffmpeg/lib
```

`Rebuilt/FastPlayer.app` にアドホック署名のアプリが生成されます。元のインストール済みアプリは変更しません。自身の利用のための同梱LGPLライブラリの変更・再リンクと、その変更のデバッグに必要なリバースエンジニアリングを認めます。詳しくはキット内の `LibraryModificationRights.txt` を参照してください。

## 配布・検証の範囲

初回公開はローカル検証版に対応します。ストア配布署名、StoreKit実取引、変更・再署名後の購入権利の維持は別途検証が必要です。このリポジトリの存在はMac App Storeでの公開完了を意味しません。
