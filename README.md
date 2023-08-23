# pubspec-metadata

GitHub Action to retrieve metadata from the pub spec.yaml file that Dart and Flutter packages have.

Inspired by [flutter-version-number-action](https://github.com/NiklasLehnfeld/flutter-version-number-action)

pubspec-metadata allows you to get the version and build number separately.

## Usage

See [action.yml](action.yml)

```yaml
- name: Pubspec Metadata
  uses: altive/pubspec-metadata@v1
  id: pubspec
  with:
    # Path to pubspec.yaml. this is needed for monorepo.
    # Default: ./pubspec.yaml
    pubspec-file: ./packages/flutter_app/pubspec.yaml

- name: Print metadata
  run: |
    echo ${{ steps.pubspec.outputs.name }}
    echo ${{ steps.pubspec.outputs.version-number }}
    echo ${{ steps.pubspec.outputs.build-number }}
```

## Outputs

### `name`

The name of the package as defined in the pubspec.yaml file.

### `version-number`

The version number of the package as defined in the pubspec.yaml file.

### `build-number`

The build number of the package as defined in the pubspec.yaml file.

It is defined following the "+" after version number.
If not defined, it will be empty.

---

- https://dart.dev/tools/pub/pubspec