# Makefile

tags: #build #Makefile

**Generate nice help output**

```makefile
help:
	@grep -E '(^[0-9a-zA-Z_-]+:.*?##.*$$)|(^##)' $(MAKEFILE_LIST) | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[32m%-25s\033[0m %s\n", $$1, $$2}' | sed -e 's/\[32m##/[33m/'

lint: ## Run lint
	$(DC_EXEC) souin /app/bin/golint ./...
```

Run make command inside target:

```makefile
build-and-run-caddy: ## Run caddy binary with the Caddyfile configuration
	$(MAKE) build-caddy
	cd plugins/caddy && ./caddy run
```