# Interoperability

Consider this standard Bitcoiner setup that Alice has: coins on a RelayX wallet, an ElectrumSV wallet, a 1SatOrdinals wallet, and a MoneyButton wallet.

<figure><img src="../.gitbook/assets/bitcache-sys arch.drawio (2).png" alt=""><figcaption></figcaption></figure>



If MoneyButton were to someday disappear, Alice should still be able to recover her wallet data since she has access to her seed master key.&#x20;

What she needs to do to recover her wallet is to take her seed and import it into a new wallet or service that will go through the **expensive** and **unreliable** process of iterating through an infinite amount of child keys and scanning the entire set of blockchain transactions to see if there is any transaction output that includes any of those child public keys.

<figure><img src="../.gitbook/assets/bitcache-sys arch.drawio (3).png" alt=""><figcaption></figcaption></figure>

Now if her wallets (or at least just the MoneyButton one) were connected to her BitCache, then this would be a non-event. Alice can, with the click of a button in seconds, move her MoneyButton seed into the Panda wallet browser extension (which will get the transaction data linked to her seed fingerprint from her BitCache) and continue using her wallet from another interface.

<figure><img src="../.gitbook/assets/bitcache-sys arch.drawio (4).png" alt=""><figcaption></figcaption></figure>

Even if her MoneyButton wallet was not connected to her BitCache, she could still use Panda wallet or more likely an external service to crawl the blockchain to find her transactions, populate her BitCache with them, and then use them in a new interface like Panda wallet.
