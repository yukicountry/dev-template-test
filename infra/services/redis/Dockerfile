FROM redis:6.0-alpine
SHELL ["/bin/ash", "-oeux", "pipefail", "-c"]

RUN apk upgrade --update && \
  apk --no-cache add tzdata && \
  # change timezone UTC to JST
  cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
  echo "Asia/Tokyo" > /etc/timezone && \
  apk del tzdata

WORKDIR /work/backend
