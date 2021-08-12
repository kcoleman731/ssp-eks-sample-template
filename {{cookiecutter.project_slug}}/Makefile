#!/bin/bash

PROJECT_SLUG := {{cookiecutter.project_slug}}
IMAGE_REPO := {{cookiecutter.image_repo}}

TS = $(shell date +%s)
HEAD_REF = $(shell git rev-list HEAD --max-count=1 --abbrev-commit)
TAG := $(HEAD_REF)_$(TS)

IMAGE_NAME = $(IMAGE_REPO)/$(PROJECT_SLUG)
TAGGED_IMAGE = $(IMAGE_NAME):$(TAG)
LATEST_IMAGE = $(IMAGE_NAME):latest

docker-build:
	@echo "Building docker container..."
	docker build \
	--cache-from=$(LATEST_IMAGE) \
	-t $(LATEST_IMAGE) \
	-t $(TAGGED_IMAGE) \
	-f Dockerfile . 

