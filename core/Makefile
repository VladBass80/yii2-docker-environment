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

# Сопутствующие команды
grunt-frontend: grunt-build
	docker run --rm -v ${PWD}/../../core/frontend/grunt:/app local/grunt npm install
	docker run --rm -v ${PWD}/../../core/frontend/grunt:/app local/grunt grunt
grunt-mobile: grunt-build
	docker run --rm -v ${PWD}/../../core/mobile/grunt:/app local/grunt npm install
	docker run --rm -v ${PWD}/../../core/mobile/grunt:/app local/grunt grunt

grunt-build:
	docker build - < dockerfiles/grunt.docker -t local/grunt
