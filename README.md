Beastsnetwork
Copyright (c) 2014-2024, The Beastsnetwork Project
Portions Copyright (c) 2012-2013 The Cryptonote developers.

Table of Contents
Development resources
Vulnerability response
Research
Announcements
Translations
Coverage
Introduction
About this project
Supporting the project
License
Contributing
Scheduled software upgrades
Release staging schedule and protocol
Compiling Beastsnetwork from source
Dependencies
Guix builds
Internationalization
Using Tor
Pruning
Debugging
Known issues
Development resources
Web: getbeastsnetwork.org
Mail: dev@getbeastsnetwork.org
GitHub: https://github.com/Beastsnetwork/beastsnetwork
IRC: #beastsnetwork-dev on Libera
It is HIGHLY recommended that you join the #beastsnetwork-dev IRC channel if you are developing software that uses Beastsnetwork. Due to the nature of this open source software project, joining this channel and idling is the best way to stay updated on best practices and new developments in the Beastsnetwork ecosystem. All you need to do is join the IRC channel and idle to stay updated with the latest in Beastsnetwork development. If you do not, you risk wasting resources on developing integrations that are not compatible with the Beastsnetwork network. The Beastsnetwork core team and community continuously make efforts to communicate updates, developments, and documentation via other platforms – but for the best information, you need to talk to other Beastsnetwork developers, and they are on IRC. #beastsnetwork-dev is about Beastsnetwork development, not getting help about using Beastsnetwork, or help about development of other software, including yours, unless it also pertains to Beastsnetwork code itself. For these cases, checkout #beastsnetwork.
Vulnerability response
Our Vulnerability Response Process encourages responsible disclosure
We are also available via HackerOne
Research
The Beastsnetwork Research Lab is an open forum where the community coordinates research into Beastsnetwork cryptography, protocols, fungibility, analysis, and more. We welcome collaboration and contributions from outside researchers! Because not all Lab work and publications are distributed as traditional preprints or articles, they may be easy to miss if you are conducting literature reviews for your own Beastsnetwork research. You are encouraged to get in touch with the Beastsnetwork research community if you have questions, wish to collaborate, or would like guidance to help avoid unnecessarily duplicating earlier or known work.

The Beastsnetwork research community is available on IRC in #beastsnetwork-research-lab on Libera, which is also accessible via Matrix.

Announcements
You can subscribe to an announcement listserv to get critical announcements from the Beastsnetwork core team. The announcement list can be very helpful for knowing when software updates are needed.
Translations
The CLI wallet is available in different languages. If you want to help translate it, see our self-hosted localization platform, Weblate, on translate.getbeastsnetwork.org. Every translation must be uploaded on the platform, pull requests directly editing the code in this repository will be closed. If you need help with Weblate, you can find a guide with screenshots here.

If you need help/support/info about translations, contact the localization workgroup. You can find the complete list of contacts on the repository of the workgroup: beastsnetwork-translations.

Coverage
Type	Status
Coverity	Coverity Status
OSS Fuzz	Fuzzing Status
Coveralls	Coveralls Status
License	License
Introduction
Beastsnetwork is a private, secure, untraceable, decentralised digital currency. You are your bank, you control your funds, and nobody can trace your transfers unless you allow them to do so.

Privacy: Beastsnetwork uses a cryptographically sound system to allow you to send and receive funds without your transactions being easily revealed on the blockchain (the ledger of transactions that everyone has). This ensures that your purchases, receipts, and all transfers remain private by default.

Security: Using the power of a distributed peer-to-peer consensus network, every transaction on the network is cryptographically secured. Individual wallets have a 25-word mnemonic seed that is only displayed once and can be written down to backup the wallet. Wallet files should be encrypted with a strong passphrase to ensure they are useless if ever stolen.

Untraceability: By taking advantage of ring signatures, a special property of a certain type of cryptography, Beastsnetwork is able to ensure that transactions are not only untraceable but have an optional measure of ambiguity that ensures that transactions cannot easily be tied back to an individual user or computer.

Decentralization: The utility of Beastsnetwork depends on its decentralised peer-to-peer consensus network - anyone should be able to run the beastsnetwork software, validate the integrity of the blockchain, and participate in all aspects of the beastsnetwork network using consumer-grade commodity hardware. Decentralization of the beastsnetwork network is maintained by software development that minimizes the costs of running the beastsnetwork software and inhibits the proliferation of specialized, non-commodity hardware.

About this project
This is the core implementation of Beastsnetwork. It is open source and completely free to use without restrictions, except for those specified in the license agreement below. There are no restrictions on anyone creating an alternative implementation of Beastsnetwork that uses the protocol and network in a compatible manner.

As with many development projects, the repository on GitHub is considered to be the "staging" area for the latest changes. Before changes are merged into that branch on the main repository, they are tested by individual developers in their own branches, submitted as a pull request, and then subsequently tested by contributors who focus on testing and code reviews. That having been said, the repository should be carefully considered before using it in a production environment, unless there is a patch in the repository for a particular show-stopping issue you are experiencing. It is generally a better idea to use a tagged release for stability.

Anyone is welcome to contribute to Beastsnetwork's codebase! If you have a fix or code change, feel free to submit it as a pull request directly to the "master" branch. In cases where the change is relatively small or does not affect other parts of the codebase, it may be merged in immediately by any one of the collaborators. On the other hand, if the change is particularly large or complex, it is expected that it will be discussed at length either well in advance of the pull request being submitted, or even directly on the pull request.
