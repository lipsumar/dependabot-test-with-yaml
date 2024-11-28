# dependabot-test

This repository is used to test the config of dependabot.

This repo is a copy of `dependabot-test`, but with a `dependabot.yml` file added with minimal config. We're confirming that adding a yaml file will opt-in to the version updates.

## Packages

### Direct dependencies

#### `ejs`

Vulnerable dependency, requires patch to fix.

- spec: `^3.1.6`
- yarn lock resolves to `3.1.6`
  - has vulnerability, fixed in `3.1.7`
- latest: `3.1.10`

#### `@babel/traverse`

Vulnerable dependency, requires minor to fix.

- spec: `^7.22.0`
- yarn lock resolves to `7.22.0`
  - has vulnerability, fixed in `7.23.2`
- latest: `7.25.9`

#### `jsonpath-plus`

Vulnerable dependency, requires major to fix.

- spec: `^9.0.0`
- yarn lock resolves to `9.0.0`
  - has vulnerability, fixed in `10.0.7`
- latest: `10.2.0`

#### `typescript`

Non-vulnerable dependency, not on latest

- spec: `^5.6.3`
- yarn lock resolves to `5.6.3`
- latest: `5.7.2`

### Transient dependencies

#### `loader-utils`

Vulnerable transient dependency, requires updates of the direct dependency.

Dependency of `babel-loader`.

- Direct dependency is `babel-loader`

  - spec: `^6.4.1`
  - yarn lock resolves to `6.4.1`
  - latest: `9.2.1` (does not depend on `loader-utils`)
  - `8.x` updates dependency to a fixed version of `loader-utils` (`2.x`)

- `loader-utils`
  - spec (through direct dependency) `^0.2.16`
  - yarn lock resolves to: `0.2.17`
    - has vulnerability, fixed in `1.4.1`
  - latest: `3.3.1`

#### `cross-spawn`

Vulnerable transient dependency, can be updated without updating the direct dependency

- Direct dependency is `webpack-cli`
  - spec: `^5.1.4`
  - yarn lock resolves to `5.1.4`
  - latest: `5.1.4`
- `cross-spawn`
  - spec (through direct dependency) `^7.0.3`
  - yarn lock resolves to `7.0.3`
    - has vulnerability, fixed in `7.0.5`
  - latest `7.0.6`
