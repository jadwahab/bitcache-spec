# Background

### History

In the past when blocks were small and Bitcoin script was limited (OP\_CODES disabled), this interoperable UX somewhat worked and it still works with other cryptocurrencies like BTC or ETH.&#x20;

You can take your 12-word mnemonic/seed phrase from one wallet interface and import it into another and you will have the same data under the hood using a new client interface - just like you would moving from Apple mail to Outlook.

The way this works is the new wallet client generates child keys from the mnemonic and then scans the entire blockchain for transaction outputs that use that address. Note that the enumeration technique used to generate child keys **must** be **standard** or else the transactions will not be found (since the keys will be different than the ones used onchain - not to mention gap limit issues and other limitations).

You should be able to see how this gets much more complicated and expensive if blocks are much bigger than 1MB, especially if different scripts and onchain protocols are used (that current indexers don't scan or filter for).



### Current state of BSV

Unfortunately, the current state of BSV infrastructure consists of some walled gardens (that don't benefit from Bitcoin's strongest asset: the ability to share data and interoperate) as well as some legacy solutions that are hanging by a thread.

Wallets like MoneyButton [dying](https://about.moneybutton.com/) should be a **non-event**. This is because you own your data since it is on a neutral data layer (the blockchain). Wallets are simply just interfaces that curate and display the data that **you own** in a nice way for you.

With the click of a button, you should be able to leave that wallet interface for another interface taking your data with you. You should not have to worry about "vendor lock-in" or getting banned and losing all of your data like you do in Web2 - that world is over.
