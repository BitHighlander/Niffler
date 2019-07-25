# Niffler Wallet

English | [简体中文](./README.zh-CN.md)

Niffler is a out-of-the box user-friendly gui [Grin](https://github.com/mimblewimble/grin) wallet.
The name 'Niffler' comes from ["harry potter"](https://harrypotter.fandom.com/wiki/Niffler).

### Latest Version: 0.4.2

v0.4.2 add a local grin full node.

It's use the official [grin-wallet v2.0.0](https://github.com/mimblewimble/grin/releases/tag/v2.0.0) and [grin v2.0.0](https://github.com/mimblewimble/grin/releases/tag/v2.0.0) as backend. 

Windows/Mac/linux version:[https://github.com/grinfans/niffler/releases/tag/v0.4.2](https://github.com/grinfans/niffler/releases/tag/v0.4.2)

Niffler wallet has a **hedwig v1 relay service**, which enable User without public ip receive grin really easy :)

In other words，**You could withdraw grin from any exchanges and miner pool effortlessly**.


## Contact

Contact me: xiaojay@gmail.com

Gitter room: https://gitter.im/niffler-wallet/community


<img src="/src/renderer/assets/logo.png" width="256"> Logo made by [@Duoasa](https://weibo.com/u/3197271025)

## Features

* Use the [official Grin binaries](https://github.com/mimblewimble/grin/releases) as back-end, and [elctron-vue](https://github.com/SimulatedGREG/electron-vue) to build gui.

* Works on mac/linux/windows, and Support multiple languages(now is for English and 简体中文)

## Screenshot

#### Create new wallet

![create new wallet](https://media.giphy.com/media/IeuEOtJvxCLqqiCCyr/giphy.gif)

#### Send grin


![send grin](https://media.giphy.com/media/LO2sAR3HmocCdbTwEh/giphy.gif)

#### Receive grin
![receive grin](https://media.giphy.com/media/iFbSw9rhh5fGVSzyZf/giphy.gif)


## Build Setup

``` bash
# clone
git clone https://github.com/grinfans/niffler.git && cd niffler

# install dependencies
npm install

# serve with hot reload at localhost:9080
npm run dev

# build electron application for production
npm run build

#Build restore node (grinRs) (install latest rustc)
npm run build-rs
mv index.node from /target to /grinRs

```

---

## Help wanted

Code pull request is always welcome.

~~More specific, it will be much appreciate if any designer from community could make a **logo** for Niffler :-)~~

We now have a wonderful logo <img src="/src/renderer/assets/logo.png" width="64"> from chinese grin community.

Logo made by [@Duoasa](https://weibo.com/u/3197271025), and also thanks [@机械师区块链](https://weibo.com/u/6318956004)

Translate to other languages is wanted, too. checkout [lang folder](https://github.com/grinfans/niffler/tree/master/src/lang).

Thanks to  [@yozx](https://github.com/yozx) for Russian version.
