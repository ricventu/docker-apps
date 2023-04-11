.DEFAULT_GOAL := up

config:
	if [ ! -f ./.env ]; then cp .env.example .env; fi

up: config
	docker-compose up -d

down:
	docker-compose down
