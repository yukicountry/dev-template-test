FROM mysql:8.0.21
SHELL ["/bin/bash", "-oeux", "pipefail", "-c"]

ENV TZ=Asia/Tokyo \
  MYSQL_ROOT_PASSWORD=mydb1234 \
  MYSQL_DATABASE=mydb \
  MYSQL_USER=mydb \
  MYSQL_PASSWORD=mydb1234

COPY ./myopt.cnf /etc/mysql/conf.d/myopt.cnf
