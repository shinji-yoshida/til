# Dockerfile 作成時に使うコマンド
```shell
# Dockerfile から image を構築。 Dockerfile を修正して何度も呼び出せる
docker image build -t [image_name] .

# image 作成 & start
docker run --name [container_name] [image_name]

# container で bash を起動
docker exec -it [container_name] bash

# container 起動と停止
docker start [container_name]
docker stop [container_name]

# host -> container へのファイルコピー
docker cp [src_path] [container_name]:[dst_path]
# container -> host へのファイルコピー
docker cp [container_name]:[src_path] [dst_path]
```
