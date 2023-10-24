# System Architecture

With your onchain data, you have two options:

1. scan _all_ network transactions after they are settled onchain, then filter and **index** the ones you need \
   _(EXPENSIVE - needs to scale as blockchain scales)_
2. **cache** transactions you need as they get settled onchain \
   _(CHEAP - only scales with your data usage)_



The BitCache system architecture aims to maintain a cache of all your blockchain transactions (regardless of which wallet or application interface you use). The idea is to create the cache at the time of transaction creation/settlement to avoid having to filter through every single network transaction. Note that network scanning/indexing can still be done to repopulate your BitCache in the case of disaster recovery.



<figure><img src="../.gitbook/assets/bitcache.drawio.png" alt="" width="476"><figcaption></figcaption></figure>

As shown in the diagram above, all of the interfaces you use to create new Bitcoin transactions - whether they are different wallet interfaces, different devices, or different Bitcoin applications - notify your BitCache of those transactions so that they are saved/cached to be used whenever and wherever you want, seamlessly.



### Admin Dashboard

Since you now have all of your onchain transactions in one place, for the first time, you can have the ability to view (without necessarily controlling) all of your transactions in one dashboard or screen.

In this dashboard, you can now see for instance that today you've created and/or received 24 payment transactions, 15 token transactions, 11 lockup transactions, 9 bSocial transactions, etc.

This changes the paradigm from transactions being **platform-based** into being **function-based**. What this means is that since you can view and use your transactions from any interface, it doesn't matter that these transactions are "HandCash" or "RelayX" transactions, it only matters what function they serve, such as payment or token transactions.



### Open Protocol

BitCache is released as an open protocol so anyone can run their own BitCache instance or use a hosted instance.
