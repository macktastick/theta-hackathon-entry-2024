# What We Learned

## RPC Clarity

We did not understand the strength of the Theta partner node offerings before we ran into some struggles with Theta's demo ETH RPC Adaptor in late May.

Now we know there is no need to rely on Theta's demo of the ETH RPC Adaptor. InfStones nodes, for example, allow us to interact with the Theta blockchain as an ETH client *or* a Theta client (two endpoints).

The demo ETH RPC Adaptor serves its purpose well for quick exercises, but *any* production application (regardless how light the usage) can *easily* make use of InfStones tiered plans - including a generous free level.

**In other words:** we appreciate Theta's decision to provide node support through partners like InfStones. We think we learned a little more about how to scale responsibly in the ecosystem.

## Leaving Read-Only Behind

Prior to this release, WWZ was a read-only Web3 application. The game relied heavily on blockchain state data, but to-date only had reason to *write* data to conventional databases.

### Automated TFUEL Reward Transactions

As part of our Summer Release, we are demonstrating a play-to-earn capability. In specific matches, the game now automatically signs and broadcasts a reward transaction to the winner.

### On-Chain Game Skins
