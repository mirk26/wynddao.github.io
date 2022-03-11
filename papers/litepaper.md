---
title: Litepaper
nav_order: 1
parent: papers
---

# Wyndex Lite Paper

```
“Clean the Planet”
```
```
Stand: Jan 25, 2022
```
Wyndex is a next-generation environmental DeFi (ReFi) project that goes beyond philanthropy by
inventing new financial instruments that provide economic return based on _verifiable_ environmental
impact. The basic value accrual and treasury mechanisms are built using similar primitives to those
driving DeFi 2.0, much like KlimaDAO. The fundamental innovation is creating new financial
primitives that can track arbitrary environmental oracle feeds, with the protocol issuing
fully-backed _long_ options to investors.

This produces a market for those who invest in the future of the planet. If off-chain projects make
verifiable positive impact, investors in that region can gain massive returns. With this building
block, we open up the door to truly decentralized innovation. The way to “game the system” and
make huge rewards is by figuring out a cheap and effective way of improving some environmental
metric. This opens up a new world of possibilities, with Web3 _inventing and validating_ new
economic and environmental models, rather than just trying to port existing markets “on-chain”.

**WYND Token Treasury**

The foundational layer of the project is the WYND token, which is minted by the protocol, and used
as the basis for all the financial products issued by the protocol. It is backed by a treasury, and the
assets-under-management provide a base value for the token, much like other reserve currencies.
Rather than solely focusing on owning its own LP token, the Wyndex treasury will also collect
stablecoins, as well as native staking tokens from aligned projects (like REGEN), and other yield
bearing tokens, which can be staked to provide a continuous income into the treasury.

The treasury will grow by issuing bonds for the tokens it wishes to add to the treasury, and minting
WYND tokens at a discount for those who buy the bonds. Each WYND token will initially be
backed by $1 worth of tokens, which provides a limit to issuance of WYND. As Wyndex progresses
and the treasury and value grow, the DAO may choose to raise this number, backing each WYND
with, say, $5 or even $50 of value to ensure a more ambitious floor price.

**Environmental Oracles**

The team has many years of experience in big data and machine learning, and members have spent
much of 2021 researching and processing the various open source environmental data sets. We will
begin using trusted data feeds from public domain NASA and ESA satellite data. As we build out a
more robust verification algorithm, we plan to include diverse inputs, such as curated lists like
restor.eco, as well as adding “ground truth” from local communities.

The team has previously prepared a 25 page whitepaper only on the subject of big data
environmental oracles, and we are happy to build out this service over time if the demand grows.
Wyndex could also offer these trusted feeds to other ReFi projects, much like the Chainlink of ReFi,
if they could use robust, verifiable feeds of diverse environmental data sets. But oracle systems only
make sense in the context of consumers, so our roadmap only focuses on the needs of Wyndex’s
environmental futures.

**Environmental Futures**


“Covered call options” or “Long-Short Pairs” are a good primitive to start modelling such
payments. We do not need any tradable token to issue them, rather we lock collateral in WYND and
use the results of an oracle at a preset date to split the collateral between the _long_ and _short_
positions. As long as the protocol is able to provide its portion of the locked collateral and we have
a reliable oracle feed, we can enable investment in any metric.

The protocol will sell these options at an algorithmically determined price to the investor,
denominated in WYND. If the protocol sells 100 options at 42 WYND, it will provide the other 58
WYND to back them. The price of such options will incorporate demand with a time decay, much
like the bond prices in Olympus Pro.

_Example: the level of air pollution in New York is 100 today. We can lock 1 WYND into an option
that covers the range 80-120, with a maturity date in 4 weeks. At the maturity date, we query the
oracle, and the value is 90, so the long receives 0.75 WYND and the short 0.25. (Note long and
short are reversed for air pollution, where a lower metric means positive environmental change).
The earnings from the short option holders feeds back into the treasury and can be used as
collateral for the next batch of options._

While these options are a viable primitive, it does have some issues in fungibility, which limit
trading these _long_ options on a secondary market beforematurity; an option issued one week has a
different strike price and maturity than one issue a week later. We are developing models based on
perpetual futures in order to provide longer lived instruments more suitable for the secondary
market, but do not require that for v1 of the protocol.

For v1, we will focus on areas where a short maturity date makes more sense, like air pollution.
Since options have a short lifetime, we can simply stop issuing them in the future and move to
different metrics, which makes them ideal for discovery of which metrics are sensible to convert
into investment vehicles.

**Environmental Impact**

As we mentioned in the introduction, our key contribution to the environment is aligning the
incentives between economic returns and environmental improvement. This will unleash the
enormous creativity currently focused on making money, often to the detriment of the environment.
Now, entrepreneurs can design new ways to improve the environment, knowing there is a clear
strategy to profit off such change.

We envision the creation of independent DAOs which will buy up options they see as “distressed”
and fund real-world projects to improve the metrics underlying the options value. Maybe they flip it
once the reforestation effort was successful, much like companies buy houses and renovate them in
order to sell at a profit. Only this time, these investors are creating positive externalities.

Although I fully believe in such DAOs, they will take some time to form and will be easier to
design when perpetual futures are implemented. In order to provide positive impact from the
beginning, we will direct 10% of the bond sales to vetted, effective environmental projects. As
web3 and cryptocurrencies are foreign to many existing non-profits, we will seek to partner with
other crypto-native projects to help serve as a bridge (EXAMPLE: what I sent in discord), but also
work to onboard mid-sized, existing organizations with strong track records.

**Governance**


This is a dynamic protocol with an ambitious roadmap and charting a new territory. As such, we
take the approach of “progressive decentralization”to provide space for the core team to innovate,
while moving essential financial decisions to the token holders as quickly as possible. The core
team cannot move the tokens in the treasury, and just ensures the initial backing and AMM
liquidity.

Once that initial liquidity is established, we will allow WYND holders to stake their tokens in order
to vote, using veWYND, based on Curve’s fantastic design. They will select which bonds Wyndex
should offer, and how many, which determines which tokens come into the treasury. These voting
token holders will also have to approve the issuance of new environmental future products as well
as discontinuing the issuance of others. This gives them control of the token issuance and treasury
and ensures no team can drain the value from the project.

Besides the “conviction voting” on which tokens to issue bonds for and futures to back, the DAO
will not be able to make many proposals itself in the short-to-mid term. Rather the core dev team
will initially retain control of the direction, retaining the exclusive right to make most proposals.
However, the DAO must vote to approve any possibly dangerous proposal, such as upgrading code
or adjusting core configuration parameters, in order to serve as a check and balance. Once the
project is more mature, and the community participates more in the manifestation of this vision,
DAO members should be able to make proposals as well.

As with the environmental impact projects, a portion of the bond sale will go to fund the core team
(including design, development, partnerships, marketing), which will be run as its own DAO. This
will initially be set to 5%. After the first 6 months, the DAO can vote to adjust this rate based on
their performance, or even vote to reward these funds to a different core team. The DAO can also
vote to adjust the percentage of the income going to the environmental projects, but cannot reduce it
below a minimum of 3%.

**Past Achievements**

● Wynd Hackatom Winner
● Support from Confio (makers of CosmWasm)
● Big data implementation
→ reached out to investors, marketing and product teams who will lead this.

**Implementation**

Wyndex will be launched as a set of CosmWasm smart contracts, on a compatible chain in the
Cosmos ecosystem (most likely, this will be Juno). Wyndex will list their token on Osmosis, using
the Liquidity Bootstrapping Pool as demonstrated by Stargaze.

**Roadmap**

_Launch Token/Treasury (April 2022)_

_Pre Launch_

```
● Community Building on Discord and Twitter
● Testnet Development and community participation to improve and build the model
efficiently
```

_Launch_

```
● WYND Token
● Fundraise initial tokens to set up AMM (using bond?)
● Liquidity Bootstraping on Osmosis
● Initial Bonds issued (LP tokens, UST, REGEN, JUNO?)
● Marketing / Awareness campaign in Cosmos
● Core Team DAO/multisig set up
● Environmental Team DAO/multisig set up with trusted key holders
● Idea: Gameify UI (no real tokens) for the Wyndex map???
```
_Plant DAO (June 2022)_

```
● veWYND design to stake and select bonds (APY% for staked tokens)
● proposal voting with veWYND to initiate/discontinue futures
● off-chain proposal forum (commonwealth?)
● DAO-DAO software on-chain?
```
_Plant Initial Futures (June 2022 - in parallel to DAO)_

```
● Initial Oracles for Air Quality
● Issue call options for 4-8 Markets (low cap on how many can be bought)
● Great UI for investors
● Onboard investments
● Issue first environmental funds
```
_Growth! (Q3-Q4 2022)_

```
● Engage the community! Active voting DAO with good focus.
○ Essential seed for future growth
● Market-test the futures offering
● Add new metrics (regions as well as land/water health)
● Bond issuance to build treasury
● Build AMM Liquidity
● Get yield from the treasury (stake assets)
● On-board more enviromental projects from the fund
```
**Future Plans**

While working on the growth phase, we have a number of items in the pipeline for possible v
based on market feedback on the product:

```
● Invest in Perpetual futures
● Ensure liquid secondary trading for the futures
● Decentralize the oracle feeds, more sustainable incentive and challenge model
● Tools to launch your own activist DAO (to “flip” options)
● Super awesome UI
● NFTs
● Implementing ARMs - Automatic regression market
● And much much more
```

