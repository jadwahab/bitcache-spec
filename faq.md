# FAQ

### What if other wallets don't use BitCache?

BitCache put the power back in the hands of the users. If a wallet does not want to cooperate with this new wallet infrastructure, then users can just as easily pull their seed from that wallet, scan the blockchain for their transactions (disaster recovery style) to populate their BitCache, and simply use another wallet interface.



### Who is BitCache targeted at? End users, wallet providers, miners?

Users. It's all about bringing ownership back into the user's hands. If a wallet or app doesn't connect to your BitCache and tries to gatekeep you away from your data, why would you use it?&#x20;



### How do I connect my BitCaches together? Can the instances could be tied together using an opt-in DHT?

Unnecessary complexity. The point is to have 1 BitCache so that you can see all of your onchain transactions in one place instead of looking for them in different places.



### Is the BitCache service operated by app/wallet provider?

The BitCache service isn’t operated by the app/wallet provider. You as a user have a relationship with your app/wallet (data curation) and then have another separate relationship with your cache layer (data ownership which you can run yourself or have it hosted).



### How does the user have data portability if the service resides with wallet / app provider?

The point is that they are separate services so that the user can have data portability. Users already _should_ have data portability because their data is onchain but the current issue is finding it (needle in a haystack style).



### User identity. How is my data segregated from other wallet/app users?

Out of scope. All the BitCache does is allow easy caching of your onchain data so it’s not so expensive to find it onchain.



### Can BitCache do identity/service discovery or transfers (like Paymail or DPP)?

Not in the scope of BitCache (separation of concerns).



### In building a non-custodial wallet one of the harder things is UTXO management. Any way in which Bitcache can mitigate the pain there would be great.

UTXO management is a _potential_ future use case but the plan is to keep things lean and simple and focused mainly on a caching layer for the blockchain.
