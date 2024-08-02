# 環境構築（MySQL+Rails7+Next.js）
詳細は、以下の記事に記載しました。  
<a href="[ここにリンク先のURLを入れる](https://nanoha-code.com/docker-rails7-nextjs-develop-environment/)" target="_blank" rel="noopener noreferrer">https://nanoha-code.com/docker-rails7-nextjs-develop-environment/</a>
  
clone後は、以下のコマンドで環境構築できる。  
   
作業ディレクトリに移動
```
cd rails-nextjs-environment/
```
ビルド   
```
docker-compose -f docker-compose-dev.yml --env-file .env.dev build
```
Dockerコンテナ立ち上げ
```
docker-compose -f docker-compose-dev.yml --env-file .env.dev up -d
```
DBの作成
```
docker-compose -f docker-compose-dev.yml --env-file .env.dev exec backend rails db:create
```
フロントエンド側のパッケージインストール
```
docker-compose -f docker-compose-dev.yml --env-file .env.dev run --rm frontend yarn install
```
Dockerコンテナ立ち上げ
```
docker-compose -f docker-compose-dev.yml --env-file .env.dev up -d
```
