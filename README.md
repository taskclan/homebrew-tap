# Taskclan Homebrew tap

```sh
brew install taskclan/tap/tsk
```

## Formulae

| Formula | What it is |
|---|---|
| [`tsk`](Formula/tsk.rb) | The Taskclan Cloud CLI — deploy, scale, tail logs and roll back from the terminal. Source: [taskclan/tsk](https://github.com/taskclan/tsk). |

## Upgrading

```sh
brew update && brew upgrade tsk
```

## Releasing a new version

1. Tag and release in [taskclan/tsk](https://github.com/taskclan/tsk).
2. `curl -sL https://github.com/taskclan/tsk/archive/refs/tags/vX.Y.Z.tar.gz | shasum -a 256`
3. Update `url` and `sha256` in `Formula/tsk.rb`, and the version in `package.json`.
4. `brew audit --formula taskclan/tap/tsk && brew install taskclan/tap/tsk && brew test tsk`

The `sha256` is what makes the download tamper-evident, so it is pinned rather
than omitted — a formula without one installs whatever the URL happens to serve
that day.
