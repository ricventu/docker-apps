.DEFAULT_GOAL := up

config:
	cp ../portainer-traefik/.env .

up: config
	docker compose up -d

down:
	docker compose down
