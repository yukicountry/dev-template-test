FROM node:10.15-alpine
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

RUN apk upgrade --update && \
  apk --no-cache add tzdata && \
  # change timezone UTC to JST
  cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  echo "Asia/Tokyo" > /etc/timezone && \
  apk del tzdata

RUN npm install -g laravel-echo-server

COPY ./laravel-echo-server.json /laravel-echo-server.json

CMD ["laravel-echo-server", "start"]
