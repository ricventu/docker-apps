.DEFAULT_GOAL := up

config:
	cp ../portainer-traefik/.env .
	if [ ! -f ./users_credentials ]; then \
		touch ./users_credentials && chmod 600 ./users_credentials && \
		htdigest users_credentials mailpit admin \
	;fi

up: config
	docker-compose up -d

down:
	docker-compose down
