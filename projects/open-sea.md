[[nft-market-places]]

### Tests

Test individual transactions
- [x]  BoredApeYachtClub https://etherscan.io/tx/0x25ddf7c03a3bf193b13f633e93dd6d2a1a3df942b76a3aa19bc3887ff1125e56
- [x] OpenSea Shared Storefront  https://etherscan.io/tx/0xdcf4809b4662c4a04709cee96f50515b13999810dd86dfa1a54371387e491f04
- [x] Sorare https://etherscan.io/tx/0x6b67140d550d574cba84772349a134d9055aa895bc8ad359e7754439f4c23894

Aggregate data test: https://duneanalytics.com/queries/66689

### Tables

Results of testing opensea / wyvern event and call tables:
`opensea."WyvernExchange_evt_OrdersMatched"`:
- field `contract_address` always contains the same value: wyvern contract address

`opensea."WyvernExchange_call_atomicMatch_"`
- field addrs [7] contains transaction currency address according to my tests
- field addrs [5] contains nft contract address according to my tests

`opensea."WyvernExchange_evt_OwnershipRenounced":
- no matching rows in Dune

`opensea."WyvernExchange_evt_OwnershipTransferred"`:
- 1 matching row in Dune from June 2018


### Research

Dune research on [[2021-06-20]] using results from:
https://duneanalytics.com/browse/dashboards?q=opensea

[[rchen8]]
https://duneanalytics.com/rchen8/opensea
- USD trade volume, # of NFTs sold, # of users - from:
	-  `wyvern."WyvernExchange_call_atomicMatch_"`
	-  `wyvern."WyvernExchange_evt_OrdersMatched"`
- monthly fees  - from:
	-  `erc20."ERC20_evt_Transfer"`
	-  `ethereum."traces"`
	
[[PierreYves_Gendron]]
https://duneanalytics.com/PierreYves_Gendron/opensea---metrics
 - USD trade volume - from:
	 -  `ethereum."transactions"`