Using Docker with Rails tutorial.

# 1. 最初の環境構築
https://docs.docker.com/samples/rails/  
ここを参考に環境構築をする。

```
first docker-compose run --no-deps web rails _6.0.4_ new hello_app --force --database=postgresql
```

```sh
sudo chown -R $USER:$USER .
```

```
docker-compose build
```