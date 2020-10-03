# コンテナ
up:
	docker-compose up
down:
	docker-compose down
build:
	docker-compose build

# 端末ログイン
web:
	docker-compose exec web ash
fpm:
	docker-compose exec fpm ash
composer:
	docker-compose run composer ash
worker:
	docker-compose exec worker ash
scheduler:
	docker-compose exec scheduler ash
db:
	docker-compose exec db bash
node:
	docker-compose run node ash
socket:
	docker-compose exec socket ash
redis:
	docker-compose exec redis ash

# DB
migrate:
	docker-compose exec fpm php artisan migrate
reset:
	docker-compose exec fpm php artisan migrate:reset
seed:
	docker-compose exec fpm php artisan db:seed
refresh:
	docker-compose exec fpm php artisan migrate:refresh
passport-install:
	docker-compose exec fpm php artisan passport:install
construct:
	@make migrate
	@make seed
	@make passport-install
reconstruct:
	@make refresh
	@make seed
	@make passport-install
sql:
	docker-compose exec db bash -c 'mysql --user=$$MYSQL_USER --password=$$MYSQL_PASSWORD --database=$$MYSQL_DATABASE'

# インストール
composer-install:
	docker-compose run composer composer install
npm-install:
	docker-compose run node npm install
