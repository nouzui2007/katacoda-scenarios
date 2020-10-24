## とにかくDockerを動かす

Dockerを動かす環境はできています。ここではとにかくDockerを動かしてみましょう。
その前に重要なワードだけ説明します。

#### イメージとは
イメージは、作りたい環境のテンプレートです。アプリケーションを動作させるのに必要なライブラリやミドルウェアがセットアップされています。
自ら作ることも、提供されているものを使うこともできます。提供されているものは、コンテナ動作に最適化するようにセットアップされているものもあります。

#### コンテナとは
ここで言うコンテナは、イメージから作られた、実際に動作している環境のことを指します。

### Hello World

プログラマにはおなじみのHello Worldをやってみましょう。

`docker run hello-world`{{execute}}

`$ docker run`は、イメージからコンテナを起動するコマンドです。

実行結果を見ていきましょう。

ローカルにhello-worldイメージがないので、Docker Hubからプルしてます。
Docker Hubは、Docker社が運営するPaaS型のDocker Registryです。

> Unable to find image 'hello-world:latest' locally
> latest: Pulling from library/hello-world
> 0e03bdcc26d7: Pull complete

これ以降が実行結果です。

> Hello from Docker!

実行結果を表示するためにDockerが行ったステップが表示されています。

1. DockerクライアントはDockerデーモンに接続
1. DockerデーモンはDocker Hubから”helloーworld＂イメージをプル
1. Dockerデーモンはプルしたイメージから新しいコンテナを作成
1. DockerデーモンはDockerクライアントに出力をストリーミング

もっと試したければubuntuコンテナを作成することが出来る、と言っています。
ちょっとやってみましょう。

`docker run -it ubuntu bash`{{execute}}

コンソールに`root@〜`と出ていれば成功です。
