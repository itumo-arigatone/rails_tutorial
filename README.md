Using Docker with Rails tutorial.

# 1. 最初の環境構築
https://docs.docker.com/samples/rails/  
ここを参考に環境構築をする。  
  
各章によってdockerを分けるようにする。  
なので、プロジェクトのファイルごとにdockerfileとdocker-compose.ymlが置いてある。(置いていく)  
  
以降は1章のhello world用のプロジェクトの環境構築手順。  
## 1.1 プロジェクトをスケルトンを使用して作る
```sh
# 1章のプロジェクトはhello_app
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
## 1.4 起動
```
docker-compose up
```

# プロジェクトができている状態から環境構築する時
途中から環境を構築すると `rails new .`をしていないため、モジュールがインストールされていない。  
なので、コンテナ内に入って`yarn install`でwbpackerをインストールする。  
```sh
sudo chown -R $USER:$USER .
```
```
docker-compose build
docker-compose up -d
docker exec -it コンテナ名 bash
```
```sh
yarn install
# 場合によっては
bundle install
```