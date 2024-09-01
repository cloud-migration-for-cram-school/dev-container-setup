FROM python:3.11

# 作業ディレクトリを設定
WORKDIR /app

# 依存関係をコピーし、インストール
COPY backend/requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# アプリケーションファイルをコピー
COPY backend /app

# FastAPIのサーバーを起動
CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "8000"]
