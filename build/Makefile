GOPATH              := $(or $(GOPATH), $(HOME)/go)
GOLINT              := golangci-lint run --timeout 10m
GO_TEST_PARALLEL    := go test -parallel $(shell nproc) -count=1
GO_TEST_INTEGRATION := go test -tags integration -p 1 -count=1


COVER_TEMP_FILE =$(shell echo "/tmp/go-cover.$$PPID.tmp")
test-cover:
	$(GO_TEST_PARALLEL) -coverprofile=$(COVER_TEMP_FILE) -covermode=count -coverpkg=./... ./... && go tool cover -html=$(COVER_TEMP_FILE) && unlink $(COVER_TEMP_FILE)

test-unit:
	$(GO_TEST_PARALLEL) -race -tags unit -v -failfast ./...

test-integration:
	$(GO_TEST_INTEGRATION) -race -v ./...

.PHONY: lint
lint:
	$(GOLINT) -v ./...