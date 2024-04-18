FROM nginx:1.24
RUN apt-get update && \
    apt-get install -y apt-utils \
    locales && \
    echo "ja_JP.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen ja_JP.UTF-8
ENV LC_ALL ja_JP.UTF-8

# インクルード用のディレクトリ内を削除
RUN rm -f /etc/nginx/conf.d/*

# Nginxの設定ファイルをコンテナにコピー
ADD nginx.conf /etc/nginx/conf.d/myapp.conf

# 初期状態の設定ファイル
# ADD ./nginx/nginx.conf /etc/nginx/nginx.conf
# ADD ./nginx/default.conf /etc/nginx/conf.d/default.conf
