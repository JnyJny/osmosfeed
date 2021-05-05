# Developer guide

## Develop

- `npm run dev`. It uses ts-node to spin up the feed builder script.
  - It will use `osmosnote.yaml` in the project root.
- To test remote caching, enable/update the cache url option inside `osmosnote.yaml`.
- To test customization, Rename `includes-test` to `includes`.

## Debug

1. Use vscode to set break point.
2. "Run and Debug".

## Publish

Currently no CI/CD integration. To publish a new version:

1. You must have permission to publish to the npm feed.
2. `npm version patch|minor|major` - updates version.
3. `npm run build` - this generates the latest binary in `bin` dir.
4. `npm publish --access public` - push to npm registry.
5. `git push origin vX.Y.Z` - publish tag to remote.
6. Add changelog as release notes in [GitHub Releases](https://github.com/osmoscraft/osmosfeed/tags).

The consumer of the builder script may need to update the dependency version to receive the latest builder script.
