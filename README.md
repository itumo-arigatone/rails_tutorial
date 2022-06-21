Using Docker with Rails tutorial.

# 1. 最初の環境構築
https://docs.docker.com/samples/rails/  
ここを参考に環境構築をする。

## 1.1 バージョンを指定してhello_appプロジェクトをスケルトンを使用して作る？
```sh
cd hello_app
docker-compose run --no-deps web rails new . --force --database=postgresql
```

## 1.2 権限設定
```sh
sudo chown -R $USER:$USER .
```

## 1.3 環境のビルド
```
docker-compose build
```