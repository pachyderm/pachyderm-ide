PACHCTL_VERSION = $(shell jq -r .pachctl ../version.json)
VERSION ?= $(shell jq -r .ide ../version.json)
.PHONY: docker-build docker-push dev-build dev-server

docker-build:
	docker build --build-arg PACHCTL_VERSION=$(PACHCTL_VERSION) --tag pachyderm/ide-user:$(VERSION) .

docker-push: docker-build
	docker push pachyderm/ide-user:$(VERSION)

dev-build:
	jlpm watch

dev-server:
	jupyter lab --watch
