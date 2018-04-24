FROM ruby:2.5

# 基本
ARG base_timezone="Asia/Tokyo"
ARG work_dir="/usr/local/share"
# Rails
ARG rails_version="5.1.4"

# 基本 ###################################
RUN apt-get update

# locale設定
RUN apt-get -y install locales
RUN locale-gen ja_JP.UTF-8
ENV LANG ja_JP.UTF-8
ENV LC_CTYPE ja_JP.UTF-8
RUN localedef -f UTF-8 -i ja_JP ja_JP.utf8

# timezone設定
ENV TZ="${base_timezone}"

# Rails ###################################
# Railsにビルド時にNode.jsが必要 
RUN apt-get install -y nodejs --no-install-recommends

# Postgresで接続
RUN apt-get install -y postgresql-client --no-install-recommends
RUN rm -rf /var/lib/apt/lists/*

# Railsインストール
RUN gem install rails --version="~>${rails_version}"

# ポート解放
EXPOSE 3000
