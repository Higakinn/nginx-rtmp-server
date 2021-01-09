# nginx-rtmp-server

# 概要
dockerを用いてローカルにrtmpサーバーを構築する

# 環境構築手順
```
$ docker-compose up -d

# 正常に起動しているかを確認する
$ docker-compose ps

          Name                   Command          State           Ports         
--------------------------------------------------------------------------------
nginx-rtmp-server_nginx-   nginx -g daemon off;   Up      0.0.0.0:1935->1935/tcp
rtmp_1         
```

# 接続テスト
obs と vlcを使用して、接続テストを行う
事前にobsとvlcをダウンロードしておく

## obsの設定
1. 設定→配信　に移動
2. サーバー欄にrtmp url を入力(ex. rtmp://0.0.0.0/live)
3. ストリームキー欄には任意のストリーム名を入力(ex. test)

## vlcの設定
1. ファイル→ネットワークを開くを選択
2. URLにobsで入力したrtmp url +　/ストリームキー　を入力 (ex. rtmp://0.0.0.0/live/test)

obs, vlc の設定が終わったら、obsの配信開始ボタンをクリック

vlcで再生できるか確認する

## ダウンロード先
- [obs](hhttps://obsproject.com/ja/download)
- [vlc](https://get.videolan.org/vlc/3.0.11.1/macosx/vlc-3.0.11.1.dmg)