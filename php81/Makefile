.DEFAULT_GOAL := all

include .env
export $(shell sed 's/=.*//' .env)

all:
	docker build -t docker-apps:php-8.1 -f ./Dockerfile \
		--build-arg INSTALL_REDIS=$(INSTALL_REDIS) \
		--build-arg INSTALL_XDEBUG=$(INSTALL_XDEBUG) \
		.
