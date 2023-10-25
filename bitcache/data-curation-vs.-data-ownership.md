# Data Curation Vs. Data Ownership

Decades of Web2 internet usage have desensitised people into thinking 2 distinct relationships are one and the same, and must exist together when using an application: the first being **data ownership** and the second being **data curation**.

**Data Ownership:** this is just the raw data. \
For example, with wallets this would be the raw transactions, or with Twetch/bSocial or Twitter this would be the data posts, comments, or likes.

**Data Curation:** this is what is done with the data itself.\
For example, with wallets this would be the interface displaying the transactions in chronological order, separating regular payments from token transfers, and allowing the creation of new payment transactions. With Twetch/bSocial or Twitter this would be the interface displaying the latest posts and offering the ability to like or comment.

### Web2

In Web2, all applications are separated walled gardens with hacky bridges and integrations at best. As shown in the diagram below, each application intricately combines data curation and data ownership. It is clear that this has become an issue with initiatives like GDPR trying to give users ownership of their data, however, technical ownership (Web3) is better than legal ownership.

<figure><img src="../.gitbook/assets/bitcache-do vs dc.drawio (2) (1).png" alt=""><figcaption></figcaption></figure>



### Web3

An example that illustrates this phenomenon clearly is Twitter. As a result of massive network effects, the barrier to entry to competing with something like Twitter has been extremely high. The only competitor with any chance of success was Threads by Meta, which only had a horse in the race because they were able to siphon their Instagram user base and network effect - and it was still really difficult. Not to mention all the issues with Twitter around banning users and effectively wiping out all of their data.&#x20;

In a Web3 world, your posts and data are onchain and you can take them wherever you go and use them from any app that curates the data in whatever way they want. For example, if you don't like the algorithm that Twitter is using to display posts to you, you can easily switch to another app which will have all the underlying data that Twitter does. Also Twitter loses their moat since any competitor will already have the same network effect that Twitter does from day 1 because the data in on a neutral layer that anyone can trust and use - not on Twitter's servers.

<figure><img src="../.gitbook/assets/bitcache-do vs dc.drawio (3) (1).png" alt=""><figcaption></figcaption></figure>

### Web3 (with BitCache)

All the BitCache infrastructure does is add a **caching layer** to make moving between different apps cheaper and easier. Notice there is now an admin dashboard in the middle between the 2 apps that you can use to view ALL of your onchain data in one place and control the data the you own.

<figure><img src="../.gitbook/assets/bitcache-do vs dc.drawio (3).png" alt=""><figcaption></figcaption></figure>

Bitcoin wallets working this way is the baseline for Web3. If simple wallets don’t work this way, then no Bitcoin application (which is a layer on top of the wallet) can.
