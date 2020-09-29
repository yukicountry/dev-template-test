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
