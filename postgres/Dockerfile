FROM postgres:latest

# 基本
ARG base_timezone="Asia/Tokyo"
ARG work_dir="/usr/local/share"
# PostgreSQL
ARG dbuser="postgres"
ARG dbpass="postgres"
ARG dbname="sample"

# 基本 ###################################
# locale設定
RUN localedef -f UTF-8 -i ja_JP ja_JP.UTF-8
ENV LANG="ja_JP.UTF-8" \
    LANGUAGE="ja_JP:ja" \
    LC_ALL="ja_JP.UTF-8"

# timezone設定
ENV TZ="${base_timezone}"

# postgres ###################################
ENV POSTGRES_USER="${dbuser}"
ENV POSTGRES_PASSWORD="${dbpass}"
ENV POSTGRES_DB="${dbname}"
