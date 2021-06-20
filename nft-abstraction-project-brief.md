# NFT abstraction

The data on NTfs is currently fragmented across dashboards, quite inaccurately reported and in general just lacking a big picture view.

We want to solve this by building an NFT abstraction that should work very similarly to dex.trades.

Initially I think it’s useful to start with the following projects and have the data of those contained in a NFT.trades table.
* Rarible
* SuperRare
* OpenSea
* CryptoPunks
add more if you find the time.

Data points of interest are:
- Sale price
- Sale unit (ETH or something else)
- USD value of sale
- Sale date
- Mint date of the NFT (if easy to implement)
- metadata like tx_hash etc.
- from and to
- Which project/platform does this NFT belong to
and whatever else you come up with in the process.

Additionally it would make sense to identify erc721 contracts by their “project name”, so it should be possible to not look at “contract 0x1823812390kalsdkjl12309” has that much volume, but rather “Bored Ape Yacht Club” has that amount of volume. We might want to solve this via our labels feature.