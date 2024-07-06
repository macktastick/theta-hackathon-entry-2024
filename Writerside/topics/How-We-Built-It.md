# How We Built It

### Architecture

The success of WWZ depends on how well it can support a growing player base. Therefore, most of our architectural design decisions favor some form of auto-scaling or serverless components.

|  ![https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/wwz-cloud-architecture-dark.png](https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/wwz-cloud-architecture-dark.png)  |
|:---------------------------------------------------------------------------------:|
|                                  *Overview of WWZ system architecture*                                   |

### UX

Players interact with the game primarily through a Discord app. We made this choice because:

* most of our potential players already have access to Discord
* it works on any popular mobile device or PC
* offloading authentication and account management to Discord enables us to move faster

Knowing we wanted to build for Discord, we attempted to follow UX flows established by the most popular Discord apps such as MidJourney.

For example, many MidJourney users are conditioned to making initial requests and options through Discord application commands.

| ![https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/sample-mj-vs-wwz-request.png](https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/sample-mj-vs-wwz-request.png) |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|                                              *Comparison of MidJourney and WWZ requests via Discord Application Commands*                                               |

And just-in-time graphics support form component choices for deeper workflows.

| ![https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/sample-mj-vs-wwz-output.png](https://s3.amazonaws.com/theta-hackathon-2024.wwz.gg/sample-mj-vs-wwz-output.png) |
|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|                                                           *Comparison of MidJourney and WWZ follow-up UIs*                                                            |

### Verification

Generally speaking, players are limited to using only NFTs they own to play WWZ. However, players do not *need* to connect a wallet to WWZ to play.

> We follow the principle of least privilege (PoLP)

Instead, we perform a Web3 version of a common Web1 security verification method: DNS-based Domain Validation (DNS-01 challenge). We provide players a unique code and ask them to place it in a location only the controller of an account could (ThetaDrop profile, OpenTheta profile, Magic Eden bio, etc.).

An example of this pattern in action can be seen in our [guide for verifying a ThetaDrop account with WWZ](https://medium.com/@wwzgame/verify-thetadrop-account-for-wwz-76eec3fcbc13).

### Summer 2024 Enhancements

Most of the Summer 2024 enhancements were built on top of existing WWZ infrastructure. However, there are some notable new components.

#### Theta Transaction Management
##### Theta Blockchain JS SDK

Automated TFUEL rewards are made possible by the [Theta Blockchain JS SDK](https://docs.thetatoken.org/docs/theta-js-sdk-overview) running in a nodejs environment.

#### Chain Readers

##### InfStones

We read data from the Theta blockchain using the [InfStones Theta API service](https://medium.com/theta-network/theta-api-service-launched-on-infstones-platform-64b7104fb7c7). This service has been so effective, we've started using it to work directly with Ethereum as well.

##### MagicEden API

For cross-community matches, we leverage the publicly available [Magic Eden API](https://docs.magiceden.io/reference/solana-overview) for data related to Solana NFTs.

##### OpenSea API

For cross-community matches, we leverage the publicly available OpenSea API for data related to Polygon NFTs.

---