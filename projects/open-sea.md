[[nft-market-places]]

Results of testing opensea / wyvern event and call tables:
`opensea."WyvernExchange_evt_OrdersMatched"`:
- field `contract_address` always contains the same value: wyvern contract address

`opensea."WyvernExchange_call_atomicMatch_"`
- field addrs [7] appears to contain transaction currency address - :todo: check
- field addrs [5] appears to contain nft contract address - :todo: check


`opensea."WyvernExchange_evt_OwnershipRenounced":
- no matching rows in Dune

`opensea."WyvernExchange_evt_OwnershipTransferred"`:
- 1 matching row in Dune from June 2018


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