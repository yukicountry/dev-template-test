# コンテナ
up:
	docker-compose -f docker-compose.yml -f docker-compose-dev.yml up

# 端末ログイン
web:
	docker-compose exec web ash
app:
	docker-compose exec app ash
composer:
	docker-compose exec composer ash
worker:
	docker-compose exec worker ash
db:
	docker-compose exec db bash
node:
	docker-compose exec node ash
redis:
	docker-compose exec redis ash
echo:
	docker-compose exec echo-server ash

# DB
migrate:
	docker-compose exec app php artisan migrate
reset:
	docker-compose exec app php artisan migrate:reset
seed:
	docker-compose exec app php artisan db:seed
refresh:
	docker-compose exec app php artisan migrate:refresh
passport-install:
	docker-compose exec app php artisan passport:install
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
