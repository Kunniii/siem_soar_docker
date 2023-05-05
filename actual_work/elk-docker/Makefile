SHELL:=/usr/bin/fish

pull:
	@docker compose pull

upd:
	@docker compose up -d

build:
	@docker compose build --no-cache

up:
	@docker compose up

down:
	@docker compose down

clean:
	@echo "Stopping Compose"
	@docker compose down
	@echo "Done"
	@echo "Removing Volmues"
	@docker volume rm (docker volume ls -q)
	@echo "Done"
