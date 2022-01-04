# CI/CD 

持续集成（`Continuous integration`）是一种软件开发实践，每次集成都通过自动化的构建（包括编译、发布 、自动化测试）来验证，从而尽早地发现集成错误。

持续部署（`Continuous deployment`）是通过自动化的构建、测试和部署循环来快速交付高质量的产品。

与 `Jenkins` 不同的是，基于 `Docker` 的 `CI/CD` 每一步都运行在 `Docker` 容器中，所以理论上支持所有的编程语言。

# GitHub Actions

[GitHub Actions](https://github.com/features/actions) 是 GitHub 推出的一款 CI/CD 工具。

我们可以在每个 `job` 的 `step` 中使用 `Docker` 执行构建步骤。

```yaml
on: push

name: CI

jobs:
  my-job:
    name: Build
    runs-on: centos-latest
    steps:
      - uses: actions/checkout@master
        with:
          fetch-depth: 2
      - name: run docker container
          uses: docker://golang:alpine
          with:
            args: go version
```

## 参考资料

- [Actions Docs](https://docs.github.com/en/actions)