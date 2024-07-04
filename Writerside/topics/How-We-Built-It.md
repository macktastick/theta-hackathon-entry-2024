# How We Built It

## WWZ At-Large

### Design

Players interact with the game primarily through a Discord app. We made this choice because:

* most of our potential players already have access to Discord
* it works on any popular mobile device or PC
* offloading authentication and account management to Discord enables us to move faster

Knowing we wanted to build for Discord, we attempted to follow UX flows similar to those established by the most popular Discord apps such as MidJourney.

For example, many MidJourney users are used to providing initial requests and options through Discord application commands.

|  ![midjourney-sample-query.png](midjourney-sample-query.png){border-effect=line}  | 
|:---------------------------------------------------------------------------------:| 
|                                  *Caption text*                                   |

| ![wwz-sample-query.png](wwz-sample-query.png){border-effect=line}  | 
|:------------------------------------------------------------------:| 
|                           *Caption text*                           |


And just-in-time graphics support form component choices for deeper workflows.

| ![midjourney-output-example.png](midjourney-output-example.png){border-effect=line}  | 
|:------------------------------------------------------------------------------------:| 
|                                    *Caption text*                                    |

| ![wwz-output-example.png](wwz-output-example.png){border-effect=line}  | 
|:----------------------------------------------------------------------:| 
|                             *Caption text*                             |

### Architecture

The success of WWZ depends on how well it can support a growing player base. Therefore, most of our architectural design decisions favor some form of auto-scaling or serverless components.

| ![wwz-cloud-architecture.png](wwz-cloud-architecture.png){border-effect=line}  | 
|:------------------------------------------------------------------------------:| 
|                *High-level look at the WWZ system architecture*                |



## Summer 2024 Enhancements

### Theta Transaction Management
#### Theta Blockchain JS SDK

### Chain Readers

#### InfStones

#### MagicEden API

#### OpenSea API