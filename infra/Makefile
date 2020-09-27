web:
	docker-compose exec web ash
app:
	docker-compose exec app ash
db:
	docker-compose exec db bash
migrate:
	docker-compose exec app php artisan migrate
sql:
	docker-compose exec db bash -c 'mysql --user=$$MYSQL_USER --password=$$MYSQL_PASSWORD --database=$$MYSQL_DATABASE'
