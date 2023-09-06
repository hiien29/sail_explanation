# Laravel sail 環境構築

## sailとは
* Laravelアプリケーションを開発するためにDockerをベースに構築された環境を提供
* PHP、MySQL、Redisを使用してLaravelアプリケーションを構築するための優れた出発点を提供

## 環境構築方法(mac)
<br>

**1.任意のディレクトリを作成し移動する(必要であれば)**

``` 
//作成したディレクトリの中にLaravelプロジェクトディレクトリが作成される

mkdir 任意のディレクトリ名
cd 任意のディレクトリ名
```
<br>
<br>

2. 下記コマンドでLaravel sailをインストール（※時間が掛かる）
「laravel-app」がLaravelプロジェクト名になります

``` 
curl -s "https://laravel.build/laravel-app" | bash
```

デフォルトではmysql、redis、meilisearch、mailhog、seleniumのコンテナが作成される
ブラウザで https://laravel.build/laravel-app で確認できる

![image](https://github.com/hiien29/sail_explanation/assets/132329554/b9d98dd2-9527-468d-90eb-62e3c70ef592)

(補足)利用したいコンテナを個別に指定できる(PostgreSQLの場合)
```
curl -s "https://laravel.build/laravel-app?with=pgsql" | bash
```

<br>
<br>

3. コマンドを実行すると途中でパスワードを求められるため自分のパソコンのパスワードを入力

![image](https://github.com/hiien29/sail_explanation/assets/132329554/1fc19794-045b-4d91-84e2-a6979e5050c0)

<br>
<br>

4. Laravelのプロジェクトに移動しDockerのイメージをビルドする
(docker buildコマンドはDocker fileからImageを作成するためのコマンド)

```
cd Laravelのプロジェクト名

./vendor/bin/sail up
```

下記URLにアクセスすると、Laravelのトップページが表示される
（他のプロジェクトを立ち上げている場合は他のプロジェクトをdocker stopさせること）
http://localhost/

<br>
<br>

5. シェルエイリアスの設定
(フルパス(./vendor/bin/sail)を省略(sail) するため)

「i」で入力可能にし、入力後「escキー」→「:wq(保存)」

```
vi ~/.zshrc

alias sail='[ -f sail ] && sh sail || sh vendor/bin/sail'
```
<br>
<br>

6. 保存した後、下記コマンドで反映

```
source ~/.zshrc
```