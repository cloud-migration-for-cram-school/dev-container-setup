#必要なNode.jsのバージョンを使用（Node 20）
FROM node:20

#作業ディレクトリを設定
WORKDIR /app

#package.jsonとpackage-lock.jsonをコピーして依存関係をインストール
COPY frontend/package.json frontend/package-lock.json /app/

#依存関係をインストール
RUN npm install

#フロントエンドのソースコードをコピー
COPY frontend /app

#ビルド（必要に応じて）
RUN npm run dev

#必要なポートを公開
EXPOSE 3000

#Viteの開発サーバーを起動
CMD ["npm", "run", "dev"]