---
title: Fairdrop
parent: WYND Token
nav_order: 2
has_children: false
has_toc: false
---

# $WYND Fairdrop

As we have seen the drama on some chains when dealing with the consequences of gamed airdrops,
we will not be releasing details of how the calculation is performed until after the snapshot is taken
and the claim period starts. We will only provide general information for now, and expand this page once
the claim period is live.

We are doing our best to make this distribution "fair". Not just by releasing 65% of the tokens to the general public,
but also in how we select the participants. We will seek to exclude any accounts tied to centralized exchanges
and only grant to people in possession of their own tokens.

## Goals of Airdrop 

Cosmos has many chains and many active contributors in many different forms. We wish to invite as many of
them to as possible to participate in the birth of the Wynd DAO. We have looked at many other airdrops
and are doing our best to learn from the successes and failures of them. One notable item is to avoid people
looking to "game the system" and quickly dump any airdropped tokens. For this reason, all airdropped
tokens will be vesting, meaning that they can be used for voting and staking from day one, but it will
take a full year until they can all be freely transferred and sold.

## Timing

We took snapshots of the relevant chains on March 28, 2022. We will perform the calculations based on
those values during the month of April. In mid to late April, we will release a site allowing you
to view how many tokens will be allocated to your address. The acutal claim period will begin late April
or early May. More exact dates will be posted as we progress on the preparations for launch.

## Multichain Claims.

You will need to provide your Juno address to view your portion and claim it, but we will match accounts
on other chains to the corresponding Juno address and perform the airdrop on one chain. This also means
you will need a 0.001 $JUNO or so to pay gas fees, which should should easily be able to get on Osmosis.

If you are in possession of your private keys in Keplr or in a Ledger, generating the Juno address should be no problem.
If your keys are stored in a local binary (say `gaiad`), you should be able to port them to another binary (`junod`), and
we hope to provide a document on how to do this for the normal case. In the worst case, you can import them
in Keplr or a Ledger if you have the mnemonic.

If you keys are held by a custodial solution, you may be out of luck and must discuss it with the custodian.
And if you manage your keys with an uncommon solution, we cannot provide support, except to show how to import your
mnemomic into another solution. 
## Fairdrop to Airdrop Calculations

**The Following Section describes the WYND token airdrop methodology for stakers and validators of different chains.**

WYND token will be getting airdropped to stakers and validators of various chains through a vesting contract. We did an analysis of data from snapshot date of these different chains and designed the formulation of reward shares for each staker & validators engaged at different levels with the chains. Majority of WYND will be airdropped to large number of stakers on different chains and some will be airdropped to validators.

### Stakers

We want to reward typical stakers by not lossing it for acoounts with negligible stake amount and also don't want to give huge amounts to whales either. 
We mapped out the staked amount, balance, and transactions sent for various chains, and put this in a chart to analyze the distribution. You can look at this example for Osmosis:

![](./imgs/Screenshot%202022-05-11%20165148.png)

**STAKED Tokens :**

What we notice. The top 1% has a HUGE amount of the money. Those are real whales.
Also, after we hit 70% or 80%, the ratio between columns increases a lot. On the bottom side, the bottom 20% or30% have 1 Osmosis or less staked, which is really like dust accounts.

**TRANSACTIONs :**

The bottom 20% have only sent 1 transaction ever. Just to stake. The top 1% have sent 100s of transactions to compound their interest. If we draw a 20%-80% line, that will range from 1 tx to 14 tx ever sent, a very reasonable range.

We actually highly punish the ones that only sent 1 tx. They never voted, nor withdrew any tokens. The ones with 3 or more are more active.

**COMMITMENT :**

We created an indicator for commitment level by finding the percentage of tokens staked in comparison to total token holdings and reward those with higher commitment to stake as compared to balance of the account.

**Formula :**

We use piecewise linear curves for all items, constant above a minimum and maximum. 

Given user $X$ is percentile $\rho$ in some metric (staked,balance,transactions,commitment), we define the reward formula as :

\begin{gather*}
Reward(R)= func(\rho_m,a,b,min,max)\\
    =a ; if \rho < min \\
    =b ; if \rho > max \\
    =a + ((b-a) * (p-min)/(max-min)) ; otherwise\\
\end{gather*}

Where a,b are for percentile cutoffs over a range of points in terms of min,max.

We chose following values for calculating individual reward points for each feature i.e. stake points, transaction points and commitment points, to be utilized as multiplier for final points calculation for a wallet.

 $$stake points = Reward(\rho(staked), 20, 80, 0, 100)$$

 $$tx multiplier = Reward(\rho(txs), 30, 90, 1, 23)$$

 $$commitment multiplier = Reward(\rho(commit), 0, 100, 1, 3)$$

$$Total Shares = (stake points * tx multiplier * commitment multiplier)$$

We then finally allocate the **Percentile Rank** for every wallet based on this total share score. If they get the same score then maximum rank is allocated to each wallet. 

### Validators

We will also reward validators from various chains. We want to reward active validators. Not just the big guys. And we want to manually filter out centralized exchanges or other “problematic” characters. We will manually make a “deny list” of validators that are either centralized exchanges, anyone offering “0% 0r 100% fee”, or otherwise known “scammy” actors in the ecosystem. These will be removed from the validator list before making all percentiles and doing the other calculations.

For validators snapshot data we mapped token staked, commission fees and number of delegators for proceeding with our formula to allocated scores to all validators active on different chains.
Validators distribution on osmosis after applying initial filters we see the following - 

![](./imgs/Screenshot%202022-05-13%20164712.png)


**Token Staked :**

There is only about a 10x change between 20% and 80%. The other extremes are quite extreme. A 10x between biggest and smallest seems rather fair.

**Number of Delegators :**

Between 20% and 80% there is a 20x difference. I am not sure this is such an important criteria at higher levels, but mainly to differentiate those who have relatively few, and those who have a larger group.The 40% is already almost 500 delegators (while 1% is only 30). Let’s just provide a multiplier over this low section and saturate at 40% (so all the rest get the same multiplier - basically a punishment for the low end)

- 0 percentile -> 20% multiplier
- 10 percentile -> 40% multiplier
- 20 percentile -> 60% multiplier
- 30 percentile -> 80% multiplier
- 40+ percentile -> 100% multiplier

**Formula :**
Similar to stakers formula used above, we calculated points based on total staked tokens by the validators and the number of delegators they have to be used as multiplier for calculating the total shares.

$$token points = Reward(\rho(tokens), 20.0, 80.0, 10, 100)$$
    
$$delegators points = Reward(\rho(stakers), 0.0, 40.0, 0.2,1)$$
    
$$Total Shares = (token points * delegators points)$$

We then finally allocate the **Percentile Rank** for every wallet based on this total share score. If they get the same score then maximum rank is allocated to each wallet.

[Vesting Details](./vesting){: .btn .btn-purple }

