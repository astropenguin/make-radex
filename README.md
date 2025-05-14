# make-radex

[![Release](https://img.shields.io/github/v/release/astropenguin/make-radex?display_name=tag&label=Release&color=cornflowerblue&style=flat-square)](https://github.com/astropenguin/make-radex/releases)
[![Tests](https://img.shields.io/github/actions/workflow/status/astropenguin/make-radex/tests.yml?label=Tests&style=flat-square)](https://github.com/astropenguin/make-radex/actions)

RADEX build by GNU Make

## Overview

This project provides a GNU Makefile for [RADEX](https://sronpersonalpages.nl/~vdtak/radex/index.shtml) that builds RADEX (see also [astropenguin/homebrew-radex](https://github.com/astropenguin/homebrew-radex.git) for the Homebrew version).
Now you can build RADEX by the following commands:

```shell
git clone https://github.com/astropenguin/make-radex.git
cd make-radex
make build
```

## RADEX commands

The following three commands and their aliases will be built:

| Command | Alias | Descripion |
| --- | --- | --- |
| `radex-1` | `radex-uni` | RADEX built with option 1 (uniform sphere) |
| `radex-2` | `radex-lvg` | RADEX built with option 2 (expanding sphere) |
| `radex-3` | `radex-slab` | RADEX built with option 3 (plane parallel slab) |

As a major difference from the normal RADEX build, the path of the data directory is not set by default:
This allows you to specify the relative or full path of a data file (`*.dat`).
Note that the tilde expansion (i.e. `~/`) cannot be used for the path specification.

## Customization

The following options can be set for the RADEX build:

| Variable | Default | Description |
| --- | --- | --- |
| `RADEX_DATADIR` | not set | Path of the directory for RADEX data files (`.dat`) |
| `RADEX_LOGFILE` | `./radex.log` | Path of the RADEX log file |
| `RADEX_MINITER` | `10` | The number of minimum iterations in a RADEX calculation |
| `RADEX_MAXITER` | `9999` | The number of maximum iterations in a RADEX calculation |

For example, if you want to set the data directory:

```shell
make build RADEX_DATADIR=${HOME}/radex
```
