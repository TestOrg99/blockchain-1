# Defining the cryptocurrency
## Solving a problem
- Why? This is the question you need to ask yourself before adding blockchain or a cryptocurrency.
- Does it needs to be decentralized? This is the second question and a very important one. Speaking for myself, getting a badge or a centralized coin will not motivate me. But cryptocurrencies are motivating, and maybe someday in the future, the coin will have a real value and will be used by anyone.
## Designing the cryptocurrency
Define the identity of the cryptocurrency:

- Purpose: Get rewarded by doing your own tasks
- Name: Motive
- Symbol: MOTIV
- Future: Give MOTIVs to different productivity products and services so that they can distribute the coins to their users in order to boost their productivity!

## Choosing a technical solution
There are many ways to build a cryptocurrency:
- ERC20 Tokens
- “Colored coin”
- Creating a clone of a Proof of Work cryptocurrency with its own blockchain
- Creating a clone of a Proof of Stake cryptocurrency with its own blockchain, it’s quite hard to find tutorials.
- Create a cryptocurrency from scratch: the hardest solution, and the longest indeed, and maybe not secured enough if you are not skilled enough.

The easiest would be to use ERC20 Tokens, the only problem is that I would have to pay fees for each transaction which makes sending 1 MOTIV per task done, a very costly action for the users! Also ERC20 uses Ethereum that uses the proof of Work consensus which is using a lot of electricity power!
## The integration with Kanbanote


#### Defining rules

The goal of Motive is to provide coins to different productivity tools that will distribute it to their users based on their own rules.
#### Defining the architecture
- Starting with 2 nodes to keep the blockchain alive
- 1 Lightweight wallet with the Kanbanote account
- Kanbanote’s backend will query the lightweight wallet that has an API in order to send a MOTIV coin every time a task is dropped in the reward column and if it hasn’t been done before.

#### Implementing it
The implementation was quite easy:

-  tried the API with the command line interface
-  created the CURL query
- updated the database in order to track if one note got already its reward and also to save the public MOTIV address and the reward column. Kanbanote does not save your private key! So you are the only owner of it, keep it safe!
- Then  implemented the UI, in order to go faster it’s a server side rendered UI with some VanillaJS to query the API.

#### Simplifying the account creation

Users have to keep this private key safe. Also in order to secure the account, it’s important to validate the account by making a transaction or clicking the validate account button in the wallet. So it’s recommended to download and run the wallet!
#### Hosting nodes
The last step before going into production was to deploy nodes. Use OVH VPS and Amazon Web Service that provides a one-year free hosting.