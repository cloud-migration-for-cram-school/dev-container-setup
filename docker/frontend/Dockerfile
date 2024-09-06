# 必要なNode.jsのバージョンを指定
FROM node:20-alpine

# 必要なパッケージをインストール（libc6-compatを追加）
RUN apk add --no-cache libc6-compat

# 作業ディレクトリを設定
WORKDIR /app

# package.jsonとpackage-lock.jsonをコピーして依存関係をインストール
COPY frontend/package.json frontend/package-lock.json /app/

# node_modulesディレクトリとpackage-lock.jsonを削除して再インストール
RUN rm -rf node_modules package-lock.json && npm cache clean --force && npm install

# Dockerfileで次を追加
RUN rm -rf node_modules package-lock.json
RUN npm install


# ソースコードをコピー
COPY frontend /app

# 必要なポートを公開
EXPOSE 5173

# Viteの開発サーバーを起動
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]
