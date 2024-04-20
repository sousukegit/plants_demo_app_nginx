FROM nginx:1.23.2
#コンフィグファイルを削除
RUN rm -f /etc/nginx/conf.d/*

RUN apt-get update && apt-get upgrade -qq && \
    apt-get install -y apt-utils \
    locales && \
    echo "ja_JP.UTF-8 UTF-8" > /etc/locale.gen && \
    locale-gen ja_JP.UTF-8
ENV LC_ALL ja_JP.UTF-8

#こちらで設定したコンフィグファイルをコンテナボリュームにコピー
COPY nginx.conf /etc/nginx/nginx.conf
#コンテナを維持するためにnginxをデーモンとして起動しない
CMD /usr/sbin/nginx -g 'daemon off;'
#ポートを80番に指定
EXPOSE 80