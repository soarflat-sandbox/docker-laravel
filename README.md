# docker-laravel

Docker で Laravel を起動するようにしたサンプル。

コンテナ起動後、以下にアクセスすればアプリケーションを確認できる。

http://127.0.0.1:10080/

## このリポジトリで利用する Docker 関連のコマンド

- `docker-compose up`
- `docker-compose down`
- `docker-compose ps`
- `docker-compose exec`

### `docker-compose up`

コンテナの作成、起動をする。

`docker-compose up`に限らず、`docker-compose`コマンドは`docker-compose.yml`が存在するディレクトリで実行する。

今回、Nginx を利用した web サーバコンテナなどを起動させるために、以下のコマンドを実行する。

```shell
$ docker-compose up -d --build
```

利用しているコマンドのオプションは以下の通り。

- `-d, --detach`: コンテナをバックグラウンドで実行する。
- `--build`: コンテナを実行する前にイメージをビルドする。変更がない場合はキャッシュが利用される。

### `docker-compose down`

`docker-compose up`で起動したコンテナを停止する。

### `docker-compose ps`

起動しているサービス（コンテナ）の一覧を表示する。

### `docker-compose exec`

指定したサービス（コンテナ）のシェルに入る。`docker exec`と同じ。

```shell
$ docker-compose exec [サービス名] [サービスで実行するコマンド]
```

今回、以下のようなコマンドを実行している。

```shell
$ docker-compose exec app ash
```

上記の場合、app という名前のサービス（コンテナ）に入り、`ash`コマンドを実行する。
