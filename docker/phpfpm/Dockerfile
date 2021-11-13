FROM ubuntu:latest

RUN apt update -y
# RUN apt install -y ubuntu-server

# タイムゾーンをJSTに
# RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# 言語を日本語に
RUN apt install -y language-pack-ja-base language-pack-ja
RUN locale-gen ja_JP.UTF-8

# PPAを有効にする
RUN apt install -y software-properties-common
RUN add-apt-repository ppa:ondrej/php
RUN apt update -y

# PHPのインストール
RUN apt install -y php8.0 php8.0-fpm

# 必要なPHPモジュールをインストール
RUN apt install -y php8.0-gd php8.0-xml php8.0-soap php8.0-mbstring php8.0-mysql

COPY ./files/entrypoint.sh /home/entrypoint.sh
RUN chmod 755 /home/entrypoint.sh

# RUN /etc/init.d/php8.0-fpm start

ENTRYPOINT /home/entrypoint.sh