# Integration

## New wallet UX flow

The way the BitCache integrates into the standard wallet user experience&#x20;



## Integration from an existing wallet

In order to plug your existing wallet into your BitCache, it is proposed that wallet clients provide an option in the wallet client settings to add your BitCache URL <mark style="color:yellow;">(or not sure if OAuth would work better).</mark>

Once your wallet client is connected to the BitCache, every time you create and broadcast a new transaction from that client, it will notify your BitCache to inform it of the spent UTXOs and new UTXOs to be added. This way, your BitCache will be updated with all of your transactions without needing to scan or index the blockchain (which is an expensive process).

## Disaster recovery from the chain

