# Fast `cargo install` action

NOTE: This is a fork of https://github.com/dtolnay/install to include packages needed by Stackable 

This GitHub Action installs a Rust crate using precompiled signed binaries built
on GitHub and hosted as GitHub release artifacts.

## Example workflow

```yaml
name: test suite
on: [push, pull_request]

jobs:
  expand:
    name: cargo udeps
    runs-on: ubuntu-latest
    steps:
      - uses: stackabletech/install@master
        with:
          crate: cargo-expand
      - run: cargo expand --help
```

<img src="https://user-images.githubusercontent.com/1940490/136493915-2c3c6a6b-620c-46e1-be4b-3c96856ccd12.png">

## Inputs

| Name    | Required | Description                                  |
| ------- | :------: | -------------------------------------------- |
| `crate` | ✓        | Name of crate as published to crates.io      |
| `bin`   |          | Name of binary; default = same as crate name |
       
### Development

Unless you're setting up an entirely new branch, work in the main branch.
When you make changes you can later run the `scripts/rebase.sh` script with the name of a branch to update.

For example:
```bash
scripts/rebase.sh cargo-udeps
```

## License

The scripts and documentation in this project are released under the [MIT
License].

[MIT License]: LICENSE
