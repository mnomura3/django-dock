FROM python:3-alpine
WORKDIR /usr/src/app
RUN apk update && apk --no-cache add \
    build-base \
    mariadb-connector-c-dev \
    mysql-client \
    vim
RUN apk --no-cache add tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk del tzdata
RUN pip install --upgrade pip && pip install \
    Django==2.2 \
    mysqlclient \
    python-dotenv
RUN export LANG="ja_JP.UTF-8"
EXPOSE 8000
