# System Architecture

{% hint style="info" %}
Main goal:

Data Ownership - AKA you can decide to leave and go somewhere else while taking your data with you wherever you go
{% endhint %}

A wallet infra service that just caches all of your onchain txs so that you don’t have to index and scan the chain

Something we’re working on that is basically just a cache of all your blockchain txs so you can easily use them across any wallet or app without needing to index the whole blockchain to find them

That way if moneybutton dies, you just take your keys and view your txs from another wallet client. And also you can view every single one of your blockchain txs in one admin dashboard (regardless what app or wallet they’re made from)

The rest of crypto kind of works this way (in a hacky way) but not bsv because blocks are bigger than 1mb and things have been mainly built around walled gardens instead of benefiting from bitcoin’s strongest asset: the ability to share data and interoperate

Wallet infra that will allow full web 3 functionality like other cryptos where everything is interoperable and you can move easily from wallet to wallet (and app to app) with your keys

Instead of the HandCash walled garden style wallets we have now

With native locking/unlocking functionality within the wallet (connected to your hardware wallet), plus an admin wallet interface where you can see all of your onchain txs from one screen.

Wallets working this way is the baseline for Web 3.0. If simple wallets don’t work this way, then no bitcoin app can.



<figure><img src="../.gitbook/assets/bitcache.drawio.png" alt="" width="476"><figcaption></figcaption></figure>

