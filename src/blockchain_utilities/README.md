# Beastsnetwork Blockchain Utilities

Copyright (c) 2014-2024, The Beastsnetwork Project

## Introduction

The blockchain utilities allow one to import and export the Beastsnetwork blockchain.

## Usage:

See also each utility's "--help" option.

### Export an existing blockchain database

`$ beastsnetwork-blockchain-export`

This loads the existing blockchain and exports it to `$BEASTSNETWORK_DATA_DIR/export/blockchain.raw`

### Import the exported file

`$ beastsnetwork-blockchain-import`

This imports blocks from `$BEASTSNETWORK_DATA_DIR/export/blockchain.raw` (exported using the `beastsnetwork-blockchain-export` tool as described above) into the current database.

Defaults: `--batch on`, `--batch size 20000`, `--verify on`

Batch size refers to number of blocks and can be adjusted for performance based on available RAM.

Verification should only be turned off if importing from a trusted blockchain.

If you encounter an error like "resizing not supported in batch mode", you can just re-run the `beastsnetwork-blockchain-import` command again, and it will restart from where it left off.

### Import options

`--input-file`
specifies input file path for importing

default: `<data-dir>/export/blockchain.raw`

`--output-file`
specifies output file path to export to

default: `<data-dir>/export/blockchain.raw`

`--block-stop`
stop at block number

`--database <database type>`

`--database <database type>#<flag(s)>`

database type: `lmdb, memory`

flags:
LMDB flags (more than one may be specified):
`nosync, nometasync, writemap, mapasync, nordahead`
