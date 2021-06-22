# Query
---
```
query trades{
  swaps(where:{pair: "0xd3d2e2692501a5c9ca623199d38826e513033a17"}, orderBy: timestamp, orderDirection: desc, first:1000, skip: 1750) {
    id
    timestamp
    amount0In
    amount1In
    amount0Out
    amount1Out
    pair {
      token0 {
        id
        symbol
        tradeVolume
        tradeVolumeUSD
        totalLiquidity
      }
      token1 {
        id
        symbol
        tradeVolume
        tradeVolumeUSD
        totalLiquidity
      }
      totalSupply
      volumeUSD
    }
    transaction {
      blockNumber
    }
  }
}
```

The [GUI](https://thegraph.com/explorer/subgraph/uniswap/uniswap-v2?query=Example%20query) allows only for 1000 queries and so we cannot get enough data for a week

# Instructions
1. Run the above query in TheGraph GUI and copy the data into a json file (already stored at `./query.json`)
2. Run all cells in the Jupyter notebook sequentially
3. The final dataframe is in `./data.csv` in the parent folder
