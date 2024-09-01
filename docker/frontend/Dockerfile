# ベースイメージとしてNode.jsを使用
FROM node:16

# 作業ディレクトリを設定
WORKDIR /app

# 依存関係をインストール
COPY frontend/package.json frontend/package-lock.json /app/
RUN npm install

# アプリケーションファイルをコピー
COPY frontend /app

# 開発サーバーを起動
CMD ["npm", "run", "dev"]
