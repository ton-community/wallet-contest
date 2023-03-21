# TON Wallet contest description

The task is to create updated versions of TON Wallet’s based on provided [mockups](https://github.com/ton-community/wallet-contest/raw/main/TON%20Wallet%20Contest.zip).

The TON Wallets are open source non-custodial wallets and are an essential part of the TON blockchain ecosystem.

Final implementations should include features listed below and should follow provided mockups and visualisations the closest possible.

The winning implementation may replace the current versions of TON Wallet.

The competition is held for four three platforms: IOS, Android, Desktop.

Desktop application’s should support three major platforms: macOS, Windows, Linux.

**Prize fund:** $60,000

**Deadline:** 22 May, 18:00 UTC

### The task

You should create TON Wallet application for chosen platform using provided mockups.

Your application should support these main features:

- creation of new wallet or importing existing one using recovery phrase
- secure wallet lock using passcode or biometrics on supported platforms
- main screen with user’s Toncoin balance and transaction’s list
- “receive Toncoin” screen with QR code
- ability to send Toncoins directly by address, by scanning QR code or via TON DNS address
- support different [wallet versions](#wallet-versions)
- [TON Connect 2.0](https://github.com/ton-connect) support

### Technical requirements

- no third party API’s for communicating with TON network are allowed
- your app should support at least last 3 major releases of target platform
- your app should only communicate with TON directly using lite-nodes via [ADNL protocol](https://ton.org/docs/develop/dapps/apis/adnl)
- wallet should not depend on any external API’s other than those needed to implement TON Connect support
- applications should be implemented using native technology of target platform (e.g. Swift for IOS, Kotlin/Java for Android, C++ for Desktop), platforms like React Native are not allowed.
- wallet should check merkle proofs of responses provided by TON network

### Deep links

Your app should support `ton://` deep links schema both for generating QR code for receiving coins and for sending coins by scanning or opening such link.

Example: `ton://transfer/<wallet_address>?amount=<amount>&text=<comment>`

Where:

- <wallet_address> is the address of recipient (both [raw and friendly](https://ton.org/docs/learn/overviews/addresses#raw-and-user-friendly-addresses) format’s could be supported)
- <amount> is the amount of coins in nanotons
- <text> is the comment for transfer

### Wallet versions

Your app should support different versions of wallet smart contract’s.

Everything in TON is a smart-contract including wallet’s and address of smart-contract (as well as the wallet) depend’s on initial data and code. This means that for given public key one can have different addresses depending on which wallet contract code is used.

Your app should support switching between `v3R1`, `v2R2` and `v4R2` wallet contracts.

You can find description and sources of wallet contract’s in official doc’s - [https://ton.org/docs/participate/wallets/contracts](https://ton.org/docs/participate/wallets/contracts)

### Communicating with TON

Since we want this wallet not to depend on third-party API’s or providers - it should connect directly to TON network using [ADNL protocol](https://ton.org/docs/develop/dapps/apis/adnl).

We recommend using the [tonlib](https://github.com/ton-blockchain/ton/tree/master/example/android) to interact with the network, but you are free to implement your own client. Note that your implementation should check Merkle proof's from network. 

### Animations

We provide all animation's in `.tgs` format which is used in Telegram animated stickers.
`.tgs` files are basically compressed Lottie animation's with some limitations.
We suggest using Telegram's rLottie fork for playing these animations: https://github.com/TelegramMessenger/rlottie

### **Resources**

- The source code of original TON Wallet for [IOS](https://github.com/ton-blockchain/wallet-ios), [Android](https://github.com/ton-blockchain/wallet-android) and [Desktop](https://github.com/ton-blockchain/wallet-desktop) are available on GitHub and can be used for the contest.
- [Official TON Docs](https://ton.org/docs)
- [TON DNS Standard](https://github.com/ton-blockchain/TEPs/blob/master/text/0081-dns-standard.md)
- Well-known TON explorers: 
  - [tonapi.io](http://tonapi.io/)
  - [tonscan.org](http://tonscan.org/)
  - [ton.cx](https://ton.cx/)
  - [tonwhales.com/explorer](https://tonwhales.com/explorer)
  - [dton.io](http://dton.io/)

### **Evaluation Criteria**

- The overall code quality, animation smoothness and overall stability.
- Ensure the app is free of major glitches, interface jumps, and severe layout issues.
- The closer your application implements the suggested mockups, the better
- Your app should run smoothly on a wide range of devices
- Security of the wallet
- Your implementation of TON Wallet should be as good or better than existing one’s
- Application size (less is better)

### **Prize distribution**
Among all the projects, we will choose who will get the prize and in what amount, due to the evaluation criteria. 

We are planning to distribute $20,000 per platform. However, the number of winning teams and the prize pool may become larger or smaller depending to the quality of the projects.

### Submit work:

- Provide a repository with your project to the [@toncontests_bot](https://t.me/toncontests_bot)
- Repository must contain **step-by-step** build instructions
- For Desktop and Android provide builds
- The repository must be public at the time of the submission deadline
- The repository should be under MIT license 
