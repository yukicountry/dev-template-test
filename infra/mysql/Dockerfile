FROM mysql:8.0.21
SHELL ["/bin/bash", "-oeux", "pipefail", "-c"]

ENV TZ=Asia/Tokyo \
  MYSQL_ROOT_PASSWORD=secret \
  MYSQL_DATABASE=youfolio-db \
  MYSQL_USER=youfolio-developer \
  MYSQL_PASSWORD=secret

COPY ./myopt.cnf /etc/mysql/conf.d/myopt.cnf
