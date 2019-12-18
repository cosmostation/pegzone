<p align="center">
 <a href="https://www.cosmostation.io" target="_blank" rel="noopener noreferrer"><img width="100" src="https://user-images.githubusercontent.com/20435620/55696624-d7df2e00-59f8-11e9-9126-edf9a40b11a8.png" alt="Cosmostation logo"></a>
</p>
<h1 align="center">
  Peg-Zone Prototype
</h1>

[Cosmostation](https://www.cosmostation.io) has been actively researching various decentralized bitcoin sidechain models and is working on building an innovative, decentralized, secure Peg Zone within [Cosmos Network](https://cosmos.network/). We presented a Peg-Zone prototype and shared our insights at the Cosmos Meetup in Seoul. 
In the PDF file below, you can check the result of every `txid` and `address` on the Bitcoin Testnet Explorer.
 Note that this prototype only demonstrates basic operations of the `Reserve Wallet` and the `Relayer` which are key components in depositing and withdrawing funds from the sidechain.
<br>

* [Peg Zone Prototype PDF](https://github.com/cosmostation/pegzone/files/3977679/peg.zone.prototype.cosmostation.20191217.pdf)

## Bridging Non-Tendermint Chains

<img width="1240" alt="pegzone1" src="https://user-images.githubusercontent.com/34641838/71065358-7345b700-21b4-11ea-9233-d413cf15f9aa.png">

Cross-blockchain crypto-asset transfer between Cosmos Hub and non-Tendermint chains that have different settlement finality require a bridge called `Peg Zone`. 
The link below will give you an in-depth explanation of a Peg Zone.
- [The Technicals of Interoperability—Introducing the Ethereum Peg-Zone](https://blog.cosmos.network/the-internet-of-blockchains-how-cosmos-does-interoperability-starting-with-the-ethereum-peg-zone-8744d4d2bc3f)

## Reserve Wallet

<img width="1385" alt="pegzone2" src="https://user-images.githubusercontent.com/34641838/71065359-7345b700-21b4-11ea-85c5-c2c819698181.png">

Based on the design of [Nomic](https://github.com/nomic-io/bitcoin-peg/blob/master/bitcoinPeg.md), you can see the `Reserve Wallet`, which is the wallet that actual Bitcoin is stored and managed in. The ownership of the `Reserve Wallet` is split into a number of validators who secure the network by using [multisignature](https://en.bitcoin.it/wiki/Multisignature) technology. As you can see in the image, each `Reserve Wallet` consists of various validators, such as A, B, C, and etc. Each validator has a specific amount of voting power(stake) in the network. `Reserve Wallet A` is created first and `Reserve Wallet E` is the most recent wallet.
<br>

<img width="1135" alt="pegzone3" src="https://user-images.githubusercontent.com/34641838/71065363-7345b700-21b4-11ea-9bd8-36916dc5207c.png">

The voting power changes as follows: `A is -30`, `C is +20`, and `E is +10` from the previous validator set of the network. If there is any change of voting power within the network, there will be an event called `checkpoint`. When a checkpoint occurs, it will create a new `Reserve Wallet`, and transfers all BTC amount from the previous wallet to the new wallet managed by a new set of validators reorganized by current voting power.
<br>

<img width="1134" alt="pegzone4" src="https://user-images.githubusercontent.com/34641838/71065364-7345b700-21b4-11ea-8cf4-558b5b0202d2.png">

There will also be a `checkpoint` when there is a new validator in the validator set or any existing validator falls out of the validator set due to different reasons. In this case, Peg Zone creates a new `Reserve Wallet D` and move all BTC from `Reserve Wallet C ` to `Reserve Wallet D`.
<br>

<img width="1135" alt="pegzone5" src="https://user-images.githubusercontent.com/34641838/71065365-73de4d80-21b4-11ea-9583-5bfcf569c0eb.png">

Let's say a user deposits BTC in `Reserve Wallet A`, `0.05 CBTC` is minted as soon as the deposit is verified. The user can withdraw this `0.05 CBTC` to the Bitcoin Network at any time through the Peg-Zone.

## Conclusion

We are actively conducting research on how we can build an innovative, decentralized, secure, user-friendly Peg Zone connecting to the Cosmos Hub. In the meantime, we are also analyzing various sidechain mechanisms used in `Nomic`, `tBTC`, `Liquid`, etc.

## Cosmostation's Services and Community

- [Official Website](https://www.cosmostation.io)
- [Mintscan Explorer](https://www.mintscan.io)
- [Web Wallet](https://wallet.cosmostation.io)
- [Android Wallet](https://bit.ly/2BWex9D)
- [iOS Wallet](https://apple.co/2IAM3Xm)
- [Telegram - International](https://t.me/cosmostation)
- [Kakao - Koreans](https://open.kakao.com/o/g6KKSe5)