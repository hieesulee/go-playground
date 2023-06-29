# go-playground

**Requirements**

- Code linter: [golangci-lint](https://golangci-lint.run/usage/install/#ci-installation):

  ```bash
  brew install golangci-lint
  ```

**MacOS**

```bash
brew install coreutils # for nproc, and makefile
```

**Commands**

- Run linter: `make lint`
- Run unit tests: `make test-unit`
- Run integration tests: `make test-integration`
- Check cover: `make test-cover`
