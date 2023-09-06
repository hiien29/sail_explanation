# Laravel sail 環境構築

## sailとは
* Laravelアプリケーションを開発するためにDockerをベースに構築された環境を提供
* PHP、MySQL、Redisを使用してLaravelアプリケーションを構築するための優れた出発点を提供

## 環境構築方法(mac)
1. 任意のディレクトリを作成し移動する（必要であれば）

``` 
//作成したディレクトリの中にLaravelプロジェクトディレクトリが作成される

mkdir 任意のディレクトリ名
cd 任意のディレクトリ名
```

2. 下記コマンドでLaravel sailをインストール（※時間が掛かる）

``` 
curl -s "https://laravel.build/laravel-app" | bash
```

デフォルトではmysql、redis、meilisearch、mailhog、seleniumのコンテナが作成される
ブラウザで https://laravel.build/laravel-app で確認できる

![image](https://github.com/hiien29/sail_explanation/assets/132329554/b9d98dd2-9527-468d-90eb-62e3c70ef592)