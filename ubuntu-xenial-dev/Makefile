NAME   := ubuntu-xenial-dev
TAG    := $$(git log -1 --pretty=%H)
IMG    := ${NAME}:${TAG}
LATEST := ${NAME}:latest

.PHONY: all

all: login test build push

test:
	@echo docker build -t ${IMG} .
	@echo docker tag ${IMG} ${LATEST}

build:
	@docker build -t ${IMG} .
	@docker tag ${IMG} ${LATEST}
	@docker tag ${IMG} ${DOCKER_USER}/${IMG}

push:
	@docker push ${DOCKER_USER}/${NAME}

login:
	@docker login --username "$$DOCKER_USER" --password "$$DOCKER_PASS"
