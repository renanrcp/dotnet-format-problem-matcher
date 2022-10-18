# Problem Matcher for dotnet-format

[![CI](https://github.com/xt0rted/dotnet-format-problem-matcher/actions/workflows/ci.yml/badge.svg)](https://github.com/xt0rted/dotnet-format-problem-matcher/actions/workflows/ci.yml)

Adds a problem matcher that will detect errors from [dotnet-format](https://github.com/dotnet/format) and create annotations for them.

## Usage

```yml
on: push
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-dotnet@v1
      - uses: renanrcp/dotnet-format-problem-matcher@v.1.3.2
      - run: dotnet tool install -g dotnet-format
      - run: dotnet-format --no-restore --verify-no-changes
```

![Example of inline annotations](docs/annotations.png)

![Example of build log with highlighted errors](docs/build-log.png)

## Options

Name | Allowed values | Description
-- | -- | --
`action` | `add` (default), `remove` | If the problem matcher should be registered or removed

## License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
