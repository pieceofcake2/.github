# ci-summary has moved

The ci-summary action now lives in its own repository:
**[pieceofcake2/ci-summary](https://github.com/pieceofcake2/ci-summary)**.

Replace

```yaml
uses: pieceofcake2/.github/actions/ci-summary@master
```

with

```yaml
uses: pieceofcake2/ci-summary@v1
```

The inputs are the same. The documentation, the tests and the release notes are in the new repository.

`action.yml` in this directory is a deprecated wrapper that calls `pieceofcake2/ci-summary@v1` with the
same inputs, so that workflows that still use `pieceofcake2/.github/actions/ci-summary@master` keep working.
It may be removed in the future.
