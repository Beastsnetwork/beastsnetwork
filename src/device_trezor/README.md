# Trezor Hardware Wallet Support for Beastsnetwork

This module adds [Trezor] hardware support to Beastsnetwork.

## Basic Information

Trezor integration is based on the following original proposal: https://github.com/ph4r05/beastsnetwork-trezor-doc

A custom high-level transaction signing protocol uses Trezor in a similar way a cold wallet is used. Transaction is built incrementally on the device. 

Trezor implements the signing protocol in [trezor-firmware] repository, in the [beastsnetwork](https://github.com/trezor/trezor-firmware/tree/master/core/src/apps/beastsnetwork) application.
Please, refer to [beastsnetwork readme](https://github.com/trezor/trezor-firmware/blob/master/core/src/apps/beastsnetwork/README.md) for more information.

## Dependencies

Trezor uses [Protobuf](https://protobuf.dev/) library.

Beastsnetwork is now compiled with C++17 by default. If you are getting Trezor compilation errors, it may be caused by abseil (protobuf dependency) not being compiled with C++17.

## Troubleshooting

To disable Trezor support, set `USE_DEVICE_TREZOR=OFF`, e.g.:

```shell
USE_DEVICE_TREZOR=OFF make release
```

## Resources:

- First pull request https://github.com/Beastsnetwork/beastsnetwork/pull/4241
- Integration proposal https://github.com/ph4r05/beastsnetwork-trezor-doc
- Integration readme in trezor-firmware https://github.com/trezor/trezor-firmware/blob/master/core/src/apps/beastsnetwork/README.md

[Trezor]: https://trezor.io/
[trezor-firmware]: https://github.com/trezor/trezor-firmware/
