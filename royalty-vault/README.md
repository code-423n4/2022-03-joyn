# Royalty Vault

This is a package which implementes logic to route secondary royalties to splitter contracts. Here is a basic understanding how it works.

##### Primary/Secondary Sales and Collection

Secondary sales are sales which are happening on marketplaces other than chestr, collection contract is a contract which is deployed by chestr producers. Collection Contract contains address of RoyaltyVault. All Royalty from secondary sales transfered to RoyaltyVault. When Transfer Event happens on Collection Contract, Royalties accumulated from previous sales get's transferred to splitter contract. Primary Sales are earnings are also being routed to RoyaltyVault.

##### Interfaces

- **IRoyaltyVault** - Contains all the methods implemented by RoyaltyVault

##### Contracts

- **RoyaltyVault** - is a main contract which contains all functionality regarding sending WETH to splitter. RoyaltyVault itself doesn't store any value in contract. RoyaltyVault Owns WETH, which can be transfered to splitter.
- **RoyaltyVaultFactory** - RoyaltyVaultFactory can be used to create RoyaltyVault, mainly used for testing purpose.
- **Mock Contracts** - Mock contracts are used for unit testing (WETH).

##### Run tests

```bash
$ npx hardhat test
```

##### Using in other project

Add below line into `package.json` dependencies and run `npm i`

```bash
"@chestrft/royalty-vault": "git+ssh://git@github.com:ChestrNFT/royalty-vault.git#development"
```

Use contracts like we do with openzepplin.

##### Happy Coding !
