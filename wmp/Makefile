up: docker-up
init: docker-down docker-pull docker-build docker-up
down: docker-down

cli:
	docker-compose exec php bash

docker-up:
	docker-compose up -d
docker-down:
	docker-compose down --remove-orphans
docker-build:
	docker-compose build
docker-pull:
	docker-compose pull