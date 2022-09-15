# taqueria-scaffold-demo
 A demo Taqueria project that comes with multiple plugins installed, a local and testnet environment config, and a LIGO source contract

| Scaffold Details   |                                                       |
|--------------------|-------------------------------------------------------|
| Complexity         | Beginner                                              |
| Automated Tests    | No                                                    |
| Installed Plugins  | LIGO, Taquito, Flextesa, Contract-Types, Tezos-Client |
| Frontend Dapp      | No                                                    |
| Wallet Integration | No                                                    |

## Requirements

- Node.js v16.x or higher
- Docker v0.8.x or higher
- Taqueria v0.3.x or higher

## Scaffold the Project

This project is available as a Taqueria scaffold. To create a new project from this scaffold, run the following command:

```shell
taq scaffold https://github.com/ecadlabs/taqueria-scaffold-demo scaffold-demo
```

This will clone the Taqueria scaffold demo project into a directory called `scaffold-demo`

Change into the project directory to get started:

```shell
cd scaffold-demo
```

## Using the Project

The intended workflow for this project is as follows:

1. Compile the LIGO source code
1. Generate contract types for the LIGO contract
1. Typecheck the compiled contract using the Tezos-Client plugin
1. Originate the smart contract to the sandbox
1. Simulate interacting with a contract entrypoint

### Compile the Contract

```shell
taq compile example.jsligo
```

This will compile the `/contracts/example.jsligo` contract to the file, `/artifacts/example.tz`. We have included a storage file `contracts/example.storages.jsligo` which will be included in the compilation process to create a default storage file which the contract will use when originating.

### Generate Contract Types for the Contract
```shell
taq generate types contract_types
```

This will search the artifacts directory and generate contract types for each tz contract found within that directory. Any files found will then have their type files output into the `contract_types` directory.

### Typecheck the Compiled Contract
We will first need to start the local sandbox that we will originate our contract to:

```shell
taq start sandbox local
```

Now we will typecheck our compiled contract against the protocol running in our sandbox

```shell
taq typecheck example.tz
```

### Originate the smart contract to the sandbox

```shell
taq originate example.tz -e sandbox
```

This will originate the example.tz contract to the local sandbox

### Simulate interacting with a contract entrypoint
```shell
taq simulate example.tz '2' --entrypoint 'increment' --storage '2' -s local
```

This simulates what would happen if the increment entrypoint was called for the example.tz contract increasing the original storage from 2 to 4
