# Add Tsunami

Tsunami is a bonding-curve token launchpad on Ink (chain id 57073). A token is
priced by its curve until the curve's sellable reserve is drained, at which
point the raise seeds a pool on Calamari and the curve closes.

##### Name (to be shown on DefiLlama): Tsunami

##### Twitter Link: https://x.com/tsunamilaunch

##### List of audit links if any: https://tsunami.trade/audit/ottersec-2026-09.pdf (OtterSec, September 2026)

##### Website Link: https://tsunami.trade

##### Logo (High resolution, will be shown with rounded borders): attached — logos/tsunami.png (1024x1024)
<img width="1024" height="1024" alt="tsunami" src="https://github.com/user-attachments/assets/a5c4f886-12de-4191-8bef-939d0a6f2340" />

##### Current TVL: ~$44.44k (quote held by bonding curves; CI snapshot, 2026-09-17 21:52:21 UTC)

##### Treasury Addresses (if the protocol has treasury): 0x686cAe1154dB17c85D2F17815Ec32eff254e1d42

##### Chain: Ink

##### Coingecko ID: none — the protocol has no token

##### Coinmarketcap ID: none — the protocol has no token

##### Short Description (to be shown on DefiLlama): Bonding-curve token launchpad on Ink.

##### Token address and ticker if any: none

##### Category: Launchpad

##### Oracle Provider(s): None. Pricing comes from the bonding curve's own reserves.

##### Implementation Details: n/a

##### Documentation/Proof: https://docs.tsunami.trade

##### forkedFrom: not a fork

##### methodology: TVL is the quote currency (native ETH or an ERC20 the factory has approved) held by the bonding curve of every token launched through the factory (0x5934a5C377309453746EE8aa5194F671930c09fa). Curves are read from the factory's getLaunchedTokens(), and each curve's quote currency from tokenQuotes(). Only the quote side is counted — the unsold launch tokens a curve holds have no price outside their own curve. A curve that graduates forwards its raise into a Calamari v4 pool and its balance goes to zero, so it stops being counted here.

##### Github org/user: private repo, not available for activity tracking

##### Does this project have a referral program? No

---

### Contracts

| | |
| --- | --- |
| Factory (proxy) | `0x5934a5C377309453746EE8aa5194F671930c09fa` |
| Curve beacon | `0x112a8B4B91aC82253f9C81D6082DD3D8e5A05CBD` |
| Hook (current; new launches) | `0x5dC5426A33c1D095B9fD0449ac16F6AaeBEeE8cc` |
| Hook (previous) | `0xbA7286377D0369F566256770Dbe2FC59D13128cC` |
| Hook (historical) | `0x110aAc8EE9cd4853fb2C12F4F73937996ECfA8CC` |

Current hook checked on-chain on 2026-09-17. Existing pools retain the hook in their pool key; the current factory hook applies to new launches. See the [deployed contract documentation](https://docs.tsunami.trade/reference/addresses.md).

### Notes

Calamari (submitted separately) is the v4 styled deployment that graduated
Tsunami tokens trade on. The two do not overlap: this adapter counts only
curves that have not graduated, and a graduated curve's balance has already
moved into Calamari's PoolManager.

### Validation

The repository's [CI TVL result](https://github.com/DefiLlama/DefiLlama-Adapters/pull/21113#issuecomment-5721728732) reported the following on 2026-09-17 21:52:21 UTC:

```text
ink                       44.44 k
total                     44.44 k
```

This is a dated USD TVL snapshot; balances and prices change over time.

