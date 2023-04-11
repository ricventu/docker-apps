.DEFAULT_GOAL := up

config:
	cp ../portainer-traefik/.env .env

up: config
	docker-compose up -d

down:
	docker-compose down
