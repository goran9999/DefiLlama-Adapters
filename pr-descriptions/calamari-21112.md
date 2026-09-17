# Add Calamari

Calamari is a v4 styled deployment on Ink (chain id 57073). It runs its own
PoolManager singleton.

##### Name (to be shown on DefiLlama): Calamari

##### Twitter Link: https://x.com/calamaridex

##### List of audit links if any: https://calamari.trade/audit/ottersec-2026-09.pdf (OtterSec, September 2026)

##### Website Link: https://calamari.trade

##### Logo (High resolution, will be shown with rounded borders): attached — logos/calamari.png (1024x1024)
<img width="1024" height="1024" alt="calamari" src="https://github.com/user-attachments/assets/56ca47c6-72ab-4e6d-bbee-f251f04d058e" />

##### Current TVL: ~$181.35k (PoolManager balances; CI snapshot, 2026-09-17 21:52:49 UTC)

##### Treasury Addresses (if the protocol has treasury): 0x686cAe1154dB17c85D2F17815Ec32eff254e1d42

##### Chain: Ink

##### Coingecko ID: none — the protocol has no token

##### Coinmarketcap ID: none — the protocol has no token

##### Short Description (to be shown on DefiLlama): Uniswap v4 DEX on Ink.

##### Token address and ticker if any: none

##### Category: Dexs

##### Oracle Provider(s): None. Calamari is a constant-function AMM and does not read an external price feed.

##### Implementation Details: n/a

##### Documentation/Proof: https://docs.calamari.trade (protocol documentation; no external oracle)

##### forkedFrom: Uniswap V4

##### methodology: TVL is the balance of every pool currency held by the Calamari PoolManager singleton (0x6E4723A612831AfB9f5B2a5aE22723c37aAB9560). v4 is a singleton, so every pool's liquidity sits in that one contract. Pool currencies are discovered from the Initialize events the PoolManager emits, which covers pools created after this PR without a code change.

##### Github org/user: private repo, not available for activity tracking

##### Does this project have a referral program? No

---

### Contracts

| | |
| --- | --- |
| PoolManager | `0x6E4723A612831AfB9f5B2a5aE22723c37aAB9560` |
| PositionManager | `0x2Fb62913fe4EE086E8F21949c5Deeb088752DC78` |
| UniversalRouter | `0x88B60D8d91457C297D50f3739481Db10c9097e5C` |
| Quoter | `0x0739Cbf29d499e8c6C3c0b2e3bC2151E986AAA3c` |
| StateView | `0x9Bf3f07e41e05D658248467760C745E278EF6211` |

### Notes

Tsunami (submitted separately) is a launchpad whose graduated tokens seed pools
on this PoolManager, so some of the TVL here is liquidity that originated
there. There is no double counting: Tsunami's TVL is the quote currency still
held by bonding curves that have not graduated, and a curve's balance moves
into a pool here only once it stops being counted there.

### Validation

The repository's [CI TVL result](https://github.com/DefiLlama/DefiLlama-Adapters/pull/21112#issuecomment-5721733173) reported the following on 2026-09-17 21:52:49 UTC:

```text
ink                       181.35 k
total                     181.35 k
```

This is a dated USD TVL snapshot; balances and prices change over time.


<!-- This is an auto-generated comment: release notes by coderabbit.ai -->

## Summary by CodeRabbit

* **New Features**
  * Added Calamari protocol coverage on the Ink network.
  * Added TVL tracking based on PoolManager-held balances.
  * Added support for discovering supported tokens from pool initialization events.
  * Included methodology details and historical tracking from the specified starting block.

<!-- end of auto-generated comment: release notes by coderabbit.ai -->
