.DEFAULT_GOAL := up

config:
	if [ ! -f ./.env ]; then cp .env.example .env; fi
	if [ ! -f ./users_credentials ]; then \
		touch ./users_credentials && chmod 600 ./users_credentials && \
		htdigest users_credentials mail admin \
	;fi


up: config
	docker-compose up -d

down:
	docker-compose down
