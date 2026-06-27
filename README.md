# Beastsnetwork

Copyright (c) 2014-2024, The Beastsnetwork Project
Portions Copyright (c) 2012-2013 The Cryptonote developers.

## Table of Contents

  - [Development resources](#development-resources)
  - [Vulnerability response](#vulnerability-response)
  - [Research](#research)
  - [Announcements](#announcements)
  - [Translations](#translations)
  - [Coverage](#coverage)
  - [Introduction](#introduction)
  - [About this project](#about-this-project)
  - [Supporting the project](#supporting-the-project)
  - [License](#license)
  - [Contributing](#contributing)
  - [Scheduled software upgrades](#scheduled-software-network-upgrades)
  - [Release staging schedule and protocol](#release-staging-schedule-and-protocol)
  - [Compiling Beastsnetwork from source](#compiling-beastsnetwork-from-source)
    - [Dependencies](#dependencies)
    - [Guix builds](#guix-builds)
  - [Internationalization](#internationalization)
  - [Using Tor](#using-tor)
  - [Pruning](#pruning)
  - [Debugging](#debugging)
  - [Known issues](#known-issues)

## Development resources

- Web: [beastsnetwork.win](https://beastsnetwork.win)
- Mail: [dev@beastsnetwork.win](mailto:dev@beastsnetwork.win)
- GitHub: [https://github.com/Beastsnetwork/beastsnetwork](https://github.com/Beastsnetwork/beastsnetwork)
- IRC: [#beastsnetwork-dev on Libera](https://web.libera.chat/#beastsnetwork-dev)
- It is HIGHLY recommended that you join the `#beastsnetwork-dev` IRC channel if you are developing software that uses Beastsnetwork. Due to the nature of this open-source software project, joining this channel and idling is the best way to stay updated on best practices and new developments in the Beastsnetwork ecosystem. All you need to do is join the IRC channel and idle to stay updated with the latest in Beastsnetwork development. If you do not, you risk wasting resources on developing integrations that are not compatible with the Beastsnetwork network. The Beastsnetwork core team and community continuously make efforts to communicate updates, developments, and documentation via other platforms — but for the best information, you need to talk to other Beastsnetwork developers, and they are on IRC. `#beastsnetwork-dev` is about Beastsnetwork development, not getting help about using Beastsnetwork, or help about development of other software, including yours, unless it also pertains to Beastsnetwork code itself. For these cases, check out `#beastsnetwork`.

## Vulnerability response

- Our [Vulnerability Response Process](https://github.com/Beastsnetwork/meta/blob/master/VULNERABILITY_RESPONSE_PROCESS.md) encourages responsible disclosure.
- We are also available via [HackerOne](https://hackerone.com/beastsnetwork).

## Research

The [Beastsnetwork Research Lab](https://src.beastsnetwork.win/resources/research-lab/) is an open forum where the community coordinates research into Beastsnetwork cryptography, protocols, fungibility, analysis, and more. We welcome collaboration and contributions from outside researchers! Because not all Lab work and publications are distributed as traditional preprints or articles, they may be easy to miss if you are conducting literature reviews for your own Beastsnetwork research. You are encouraged to get in touch with the Beastsnetwork research community if you have questions, wish to collaborate, or would like guidance to help avoid unnecessarily duplicating earlier or known work.

The Beastsnetwork research community is available on IRC in [#beastsnetwork-research-lab on Libera](https://web.libera.chat/#beastsnetwork-research-lab), which is also accessible via Matrix.

## Announcements

- You can subscribe to an [announcement listserv](https://lists.beastsnetwork.win) to get critical announcements from the Beastsnetwork core team. The announcement list can be very helpful for knowing when software updates are needed.

## Translations

The CLI wallet is available in different languages. If you want to help translate it, see our self-hosted localization platform, Weblate, on [translate.beastsnetwork.win](https://translate.beastsnetwork.win/projects/beastsnetwork/cli-wallet/). Every translation *must* be uploaded on the platform. Pull requests directly editing the code in this repository will be closed. If you need help with Weblate, you can find a guide with screenshots [here](https://github.com/beastsnetwork-ecosystem/beastsnetwork-translations/blob/master/weblate.md).

If you need help/support/info about translations, contact the localization workgroup. You can find the complete list of contacts on the repository of the workgroup: [beastsnetwork-translations](https://github.com/beastsnetwork-ecosystem/beastsnetwork-translations#contacts).

## Coverage
   Type       | Status |
 |------------|--------|
 | Coverity   | [![Coverity Status](https://scan.coverity.com/projects/9657/badge.svg)](https://scan.coverity.com/projects/9657/) |
 | OSS Fuzz   | [![Fuzzing Status](https://oss-fuzz-build-logs.storage.googleapis.com/badges/beastsnetwork.svg)](https://bugs.chromium.org/p/oss-fuzz/issues/list?sort=-opened&can=1&q=proj:beastsnetwork) |
 | Coveralls  | [![Coveralls Status](https://coveralls.io/repos/github/Beastsnetwork/beastsnetwork/badge.svg?branch=master)](https://coveralls.io/github/Beastsnetwork/beastsnetwork?branch=master) |
 | License    | [![License](https://img.shields.io/badge/license-BSD3-blue.svg)](https://opensource.org/licenses/BSD-3-Clause) |

## Introduction

Beastsnetwork is a private, secure, untraceable, decentralized digital currency. You are your bank, you control your funds, and nobody can trace your transfers unless you allow them to do so.

**Privacy:** Beastsnetwork uses a cryptographically sound system to allow you to send and receive funds without your transactions being easily revealed on the blockchain (the ledger of transactions that everyone has). This ensures that your purchases, receipts, and all transfers remain private by default.

**Security:** Using the power of a distributed peer-to-peer consensus network, every transaction on the network is cryptographically secured. Individual wallets have a 25-word mnemonic seed that is only displayed once and can be written down to back up the wallet. Wallet files should be encrypted with a strong passphrase to ensure they are useless if ever stolen.

**Untraceability:** By taking advantage of ring signatures, a special property of a certain type of cryptography, Beastsnetwork is able to ensure that transactions are not only untraceable but have an optional measure of ambiguity that ensures that transactions cannot easily be tied back to an individual user or computer.

**Decentralization:** The utility of Beastsnetwork depends on its decentralized peer-to-peer consensus network. Anyone should be able to run the Beastsnetwork software, validate the integrity of the blockchain, and participate in all aspects of the Beastsnetwork network using consumer-grade commodity hardware. Decentralization of the Beastsnetwork network is maintained by software development that minimizes the costs of running the Beastsnetwork software and inhibits the proliferation of specialized, non-commodity hardware.

## About this project

This is the core implementation of Beastsnetwork. It is open-source and completely free to use without restrictions, except for those specified in the license agreement below. There are no restrictions on anyone creating an alternative implementation of Beastsnetwork that uses the protocol and network in a compatible manner.

As with many development projects, the repository on GitHub is considered to be the "staging" area for the latest changes. Before changes are merged into that branch on the main repository, they are tested by individual developers in their own branches, submitted as a pull request, and then subsequently tested by contributors who focus on testing and code reviews. That having been said, the repository should be carefully considered before using it in a production environment, unless there is a patch in the repository for a particular show-stopping issue you are experiencing. It is generally a better idea to use a tagged release for stability.

**Anyone is welcome to contribute to Beastsnetwork's codebase!** If you have a fix or code change, feel free to submit it as a pull request directly to the `master` branch. In cases where the change is relatively small or does not affect other parts of the codebase, it may be merged in immediately by any one of the collaborators. On the other hand, if the change is particularly large or complex, it is expected that it will be discussed at length either well in advance of the pull request being submitted or even directly on the pull request.

## Supporting the project

Beastsnetwork is a 100% community-sponsored endeavor. If you want to join our efforts, the easiest thing you can do is support the project financially. Both Beastsnetwork and Bitcoin donations can be made to **donate.beastsnetwork.win** if using a client that supports the [OpenAlias](https://openalias.org) standard. Alternatively, you can send BEAST to the Beastsnetwork donation address via the `donate` command (type `help` in the command-line wallet for details).

The Beastsnetwork donation address is:
`888tNkZrPN6JsEgekjMnABU4TBzc2Dt29EPAvkRxbANsAnjyPbb3iQ1YBRk1UXcdRsiKc9dhwMVgN5S9cQUiyoogDavup3H`

Viewkey:
`f359631075708155cc3d92a32b75a7d02a5dcf27756707b47a2b31b21c389501`

Base address for restoring with address and viewkey:
`44AFFq5kSiGBoZ4NMDwYtN18obc8AemS33DBLWs3H7otXft3XjrpDtQGv7SqSsaBYBb98uNbr2VBBEt7f2wfn3RVGQBEP3A`

The Bitcoin donation address is:
`1KTexdemPdxSBcG55heUuTjDRYqbC5ZL8H`

Core development funding and/or some supporting services are also graciously provided by [sponsors](https://www.beastsnetwork.win/community/sponsorships/):

[<img width="150" src="https://www.beastsnetwork.win/img/sponsors/tarilabs.png"/>](https://tarilabs.com/)
[<img width="150" src="https://www.beastsnetwork.win/img/sponsors/symas.png"/>](https://symas.com/)
[<img width="150" src="https://www.beastsnetwork.win/img/sponsors/macstadium.png"/>](https://www.macstadium.com/)

There are also several mining pools that kindly donate a portion of their fees. A list of them can be found on our [Bitcointalk post](https://bitcointalk.org/index.php?topic=583449.0).

## License

See [LICENSE](LICENSE).

## Contributing

If you want to help out, see [CONTRIBUTING](docs/CONTRIBUTING.md) for a set of guidelines.
