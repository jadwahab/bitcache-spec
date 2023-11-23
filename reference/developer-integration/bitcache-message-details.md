# BitCache Message Details

The BitCache message structure is one of length-delimited chunks of bytes with the following parts:

{% hint style="info" %}
### Serialisation format <a href="#docs-internal-guid-3af620bf-7fff-e7e2-b09d-954e512e354d" id="docs-internal-guid-3af620bf-7fff-e7e2-b09d-954e512e354d"></a>

Each chunk in a BitCache channel message has the following header:

`8 byte chunk name`

`8 byte chunk size`
{% endhint %}

| Chunk               | Chunk details                                                                        | Example (as hex)   |
| ------------------- | ------------------------------------------------------------------------------------ | ------------------ |
| Transaction         | A chunk that includes a serialised transaction.                                      | `545842595445532e` |
| Key usage metadata. | A chunk that defines key usage metadata in the outputs of the preceding transaction. | `54584f4b4559532e` |

Transaction chunk structure

| Fields      | Details                                                                                                                                | Example (as hex)                                                            |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| Chunk name  | The "TXBYTES.." characters.                                                                                                            | `545842595445532e`                                                          |
| Chunk size  | The size of the chunk data. In this case this will be the size of the raw transaction bytes, as it is the only contents of this chunk. | `2e01000000000000`                                                          |
| Transaction | The raw transaction bytes.                                                                                                             | See the example data value for "Transaction" for a hex-encoded transaction. |

Output key usage chunk structure

| Fields                            | Details                                                                                                       | Example (as hex)   |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------ |
| Chunk name                        | The "TXOKEYS." characters.                                                                                    | `54584f4b4559532e` |
| Chunk size                        | The size of the chunk data. In this case, it will be the total length of all included txo key usage metadata. |                    |
| N txo key usage metadata entries. | See the Key usage metadata structure.                                                                         |                    |

Key usage metadata structure

| Field                  | Details                                                                                               | Example                                                                                               |
| ---------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| TXO index              | Unsigned 32 bit little endian encoding of the relevant output index.                                  | `01000000`                                                                                            |
| Script type            | Script type length (unsigned 16 bit little endian encoding) followed by the script type name.         | `05007032706b68` = `0500` + `7032706b68`(script type "p2pkh")                                         |
| Parent key fingerprint | Fingerprint length (unsigned 16 bit little endian encoding) followed by the fingerprint bytes.        | `04009341cb4c` = `0400` + `9341cb4c`                                                                  |
| Key derivation         | Derivation path length (unsigned 16 bit little endian encoding) followed by the derivation path text. | `0c0062697033323a6d2f302f3130` = `0c00` + `62697033323a6d2f302f3130` (derivation path "bip32:m/0/10") |

Example data values

| Field                | Details                                                                   | Example                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Transaction          | Raw transaction bytes                                                     | `0100000001ad9ae96078e5b800befd94ce7c76e954ede0ee4c44658027b890b6dc12b255a9010000006b483045022100eb5da30e41c5e845067dce7bb69374ea0326f3838fb88329c3f05108cc834e43022009e8863aa5f1ade4297910855ca01cd43c121bbd229b70239acc15c542670d814121030e1712ce957f9b6c767e7c77d53f72431a21039cf4a9d0cd2561b56739dcf5b3ffffffff0201000000000000006576a914192ef569a938fbbd9e7e70d6006c752ee3894b1288ac0063036f72645118746578742f706c61696e3b636861727365743d7574662d3800297b2270223a22736e73222c226f70223a22726567222c226e616d65223a22313939392e73617473227d681938e307000000001976a91417d75b01333740da28202e082bc2540b1989dbc088ac00000000` |
| Output Index         | Output index (vout) a key is used in                                      | `2`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Seed/Key Fingerprint | A unique identifier to specify which seed/master key is used              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Derivation           | The derivation method and the derivation path used (separated by a colon) | <p><code>bip32:m/44'/236'/0'/0</code></p><p><code>/0</code></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Script Type          | The script type(s) used in that transaction output                        | `p2pkh` `p2ms` `ord`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |





### Seed/Key Fingerprint

Electrum wallets build on the BIP32 fingerprint. This is what is included into a BIP32 xpub and will likely be good enough for our needs. This is the first four bytes of the ripemd160 hash of the parent public key.

So wherever Electrum wallets have a need for fingerprints the following is done:

* For single singer wallets this is the first four bytes of the ripemd160 hash of the parent key. This is 4 bytes long.
* For multi-signature wallets, the fingerprint of each cosigner wallet is taken as per the single signer case, then they are ordered and concatenated. For n cosigners, this is n\*4 bytes long.
