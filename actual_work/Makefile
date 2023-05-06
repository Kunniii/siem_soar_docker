SHELL:=/usr/bin/fish

init:
	@docker network create --driver bridge siem_soar

pull:
	@docker compose -f ./elk_docker/docker-compose.yaml pull
	@docker compose -f ./thehive_cortex_docker/docker-compose.yaml pull

elk-build:
	@docker compose -f ./elk_docker/docker-compose.yaml build --no-cache

hivecortex-build:
	@docker compose -f ./thehive_cortex_docker/docker-compose.yaml build --no-cache

elk-up:
	@docker compose -f ./elk_docker/docker-compose.yaml up -d

hivecortex-up:
	@docker compose -f ./thehive_cortex_docker/docker-compose.yaml up -d

elk-down:
	@docker compose -f ./elk_docker/docker-compose.yaml down

hivecortex-down:
	@docker compose -f ./thehive_cortex_docker/docker-compose.yaml down

up: elk-up hivecortex-up

build: elk-build hivecortex-build

clean:
	@echo "Stopping Compose"
	@docker compose -f ./thehive_cortex_docker/docker-compose.yaml down
	@docker compose -f ./elk_docker/docker-compose.yaml down
	@echo "Done"
	@echo "Removing Volmues"
	@docker volume rm (docker volume ls -q)
	@echo "Done"
