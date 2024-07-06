# Challenges We Ran Into

### ETH RPC Adaptor

In early June, the game began intermittently having trouble reading data from the Theta blockchain. We were able to trace the issue to our communications with the Theta ETH RPC Adaptor failing.

[Theta's documentation on this service](https://docs.thetatoken.org/docs/web3-stack-eth-rpc-support) is clear: it is only meant for light usage. So we assumed we may be the problem and looked at other options for ETH-to-Theta RPC support, including hosting our own.

This [InfStones Partnership Announcement](https://medium.com/theta-network/theta-api-service-launched-on-infstones-platform-64b7104fb7c7) from 2023 piqued our interest. We tried the service, ran a series of simulated games with it, and found it to be reliable and performant. We have been running it in production without issue ever since.

### 3rd Party On-Chain Data Failure

Between May and mid-June, we depended on a 3rd party, premium service for querying the Solana blockchain in a reliable and efficient manner. On June 18th, it suddenly stopped working. Nothing in our related code changed. Their support offered no response. We still don't know what happened.

We reviewed several Solana data providers and ultimately found everything we needed in the [Magic Eden API](https://docs.magiceden.io/reference/solana-overview) with one catch. Our busiest game lobbies, where several players take Training actions nearly simultaneously, are likely to violate rate limits for normal API usage. We were lucky enough Magic Eden accepted our request for elevated API usage and have been able to completely circumvent the problem.

### Contract Deployment Issues

In June, we began minting the skins awarded to Players on the Theta blockchain. Our first attempts at a contract following an [**older** Theta demonstration](https://docs.thetatoken.org/docs/creating-nfts-on-theta-blockchain) led to a couple of smaller challenges.

#### Error Messages on Deploy

We received errors messages when deploying a contract using the latest version of OpenZeppelin Contract Wizard and Remix. We learned of complexities with using the latest version of the EVM compiler and possible solutions through Discord help messages by **@Pizajolo** from April 2024.

#### Popular Toolset (In)Compatibility

With the caveat that we are not experts with the tools in question, using an earlier version of the EVM compiler (per above) meant we could not use some popular applications like the OpenZeppelin Contract Wizard (maybe possible using old builds?).

We ended up piecing our contract together from existing Theta documentation and working examples.

We think if there's a way to bridge this (temporary?) gap - how to use popular, current tools with output Theta accepts today - more groups like us could explore Theta more easily.

### Scoring Information Architecture

Cross-Community matches posed a design challenge: how do we quickly convey the state of a Team of arbitrary size?

In previous game formats, we primarily relied on well-formated, text-based lists of combatants and players. These text-based leaderboards don't *quickly* convey the necessary information in a team vs. team setting. Good for a *detailed* look, they make viewing a live match tedious *or* even boring if a viewer simply skips reading scoreboards altogether.

We landed on a visual solution that leverages our strengths in near real-time image processing. We still provide a text-based list of combatants in scoreboards, but we include something we call Facewalls as well.

A Facewall is a grid of all team member PFPs and visual indicators of critical states (low health, energy, death).

| ![https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/facewall-whiteboard.png](https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/facewall-whiteboard.png)  |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|                                                                *Designing the Facewall feature*                                                                |

---