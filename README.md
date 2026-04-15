# setup-anyzig

GitHub Action to install [anyzig](https://github.com/marler8997/anyzig) so that
`zig` is available in PATH. By default, anyzig will use the version declared in
build.zig.zon. I also enables testing with multiple zig versions by passing
the version as the first argument (e.g. `zig 0.14.1 build`).

## Usage

```yaml
- uses: marler8997/setup-anyzig@master
- run: zig build
- run: zig 0.14.1 build
```

## Inputs

| Input | Description | Default |
|-------|-------------|---------|
| `use-cache` | Cache the global Zig cache directory between runs | `true` |
| `cache-key` | Additional cache key component for distinguishing matrix jobs (OS and job name are included automatically) | `''` |

## Platforms

Works on all GitHub-hosted runner OSes:

- `ubuntu-latest`
- `macos-latest`
- `windows-latest`

## What is anyzig?

[anyzig](https://github.com/marler8997/anyzig) is a drop-in replacement for the
`zig` command that can run any version of the Zig compiler. When invoked as
`zig`, it reads `build.zig.zon` to determine the correct version. You can also
request a specific version directly: `zig 0.14.1 build test --summary all`.
