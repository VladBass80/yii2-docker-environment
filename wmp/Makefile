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
	docker run --rm -v ${PWD}/../../wmp-core:/app --workdir /app/frontend/grunt local/grunt npm install
	docker run --rm -v ${PWD}/../../wmp-core:/app --workdir /app/frontend/grunt local/grunt grunt
grunt-mobile: grunt-build
	docker run --rm -v ${PWD}/../../wmp-core:/app --workdir /app/mobile/grunt local/grunt npm install
	docker run --rm -v ${PWD}/../../wmp-core:/app --workdir /app/mobile/grunt local/grunt grunt mobile

grunt-build:
	docker build - < dockerfiles/grunt.docker -t local/grunt
