# Template for starknet.dart workshop

## Dependencies

- [scarb](https://docs.swmansion.com/scarb)
- [starkli](https://book.starkli.rs/)
- [poetry](https://python-poetry.org/)
  
### Version management:
Scarb version is managed with [asdf](https://asdf-vm.com/guide/getting-started.html)
Python is managed with [pyenv](https://github.com/pyenv/pyenv)

## Directories

### app

Contains `pubspec_overrides.yaml` to force `starknet` and `starknet_builder` coming from github.

### contracts

Contains source code for Cairo contract

### devnet

Contains setup to run a local devnet.

To start devnet:
```
$ make devnet
```

If you have an issue when declaring a contract, it could be related to permission of starknet compiler in cairo-lang package.

You can run the following command to fix it:
```
make fixup
```

The path to directory containing starknet compilers when using poetry should be:
`${HOME}/.cache/pypoetry/virtualenvs/${env_name}/lib/${python_version}/site-packages/starkware/starknet/compiler/v1/bin`

### tool

Contains a dart script to extract ABI part from a Sierra json file.

Usage:
```
$ dart pub get
$ dart run ./bin/extract_sierra_json.dart --input SIERRA.json --output ABI.json
```
