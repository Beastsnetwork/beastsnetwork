# Bootstrappable Beastsnetwork Builds

This directory contains the files necessary to perform bootstrappable Beastsnetwork builds.

[Bootstrappability](https://bootstrappable.org/) furthers our binary security guarantees by allowing us to _audit and reproduce_ our toolchain instead of blindly _trusting_ binary downloads.

We achieve bootstrappability by using Guix as a functional package manager.

# Requirements

Conservatively, you will need an x86_64 machine with:

- 16GB of free disk space on the partition that /gnu/store will reside in
- 8GB of free disk space **per platform triple** you're planning on building

# Installation and Setup

If you don't have Guix installed and set up, please follow the instructions in [INSTALL.md](./INSTALL.md)

# Usage

To build Beastsnetwork reproducibly with all default options, invoke the following from the top of a clean repository:

```sh
./contrib/guix/guix-build
```

## Cleaning intermediate work directories

By default, `guix-build` leaves all intermediate files intact. The `guix-clean` script can clean the current git worktree:

```
./contrib/guix/guix-clean
```

## Attesting to build outputs

After you've cloned the `guix.sigs` repository, to attest to the current worktree's commit/tag:

```
env GUIX_SIGS_REPO=<path/to/guix.sigs> SIGNER=<gpg-key-name> ./contrib/guix/guix-attest
```

## Verifying build output attestations

After at least one other signer has uploaded their signatures to the `guix.sigs` repository:

```
git -C <path/to/guix.sigs> pull
env GUIX_SIGS_REPO=<path/to/guix.sigs> ./contrib/guix/guix-verify
```

## Common guix-build invocation patterns

### Building a subset of platform triples

```sh
env HOSTS='x86_64-w64-mingw32 x86_64-apple-darwin' ./contrib/guix/guix-build
```

### Controlling the number of threads

```sh
export ADDITIONAL_GUIX_COMMON_FLAGS='--max-jobs=8'
```

## Recognized environment variables

* **HOSTS**: Override the space-separated list of platform triples
* **SOURCES_PATH**: Set the depends tree download cache for sources
* **BASE_CACHE**: Set the depends tree cache for built packages
* **JOBS**: Override the number of jobs to run simultaneously
* **V**: If non-empty, will pass `V=1` to all `make` invocations
* **SUBSTITUTE_URLS**: A whitespace-delimited list of URLs for pre-built packages
* **ADDITIONAL_GUIX_COMMON_FLAGS**: Additional flags for all `guix` commands

# Choosing your security model

Guix allows us to achieve better binary security by using our CPU time to build everything from scratch. Users can decide whether or not to use **substitutes** (pre-built packages).

## Option 1: Building with substitutes

Authorize the signing keys and use the official Guix build farm.

## Option 2: Disabling substitutes

For direct invocations of `guix`:
```sh
guix <cmd> --no-substitutes
```

For the scripts under `./contrib/guix/`:
```sh
export ADDITIONAL_GUIX_COMMON_FLAGS='--no-substitutes'
```

## Option 3: Disabling substitutes by default

`guix-daemon` accepts a `--no-substitutes` flag.
