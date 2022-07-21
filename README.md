# taqueria-scaffold-demo
 A demo Taqueria project that comes with all plugins installed, a local and testnet envorinment config, and a LIGO source contract

## Requirements

- Node.js v16.x oor higher
- Docker v0.8.x or higher
- Taqueria v0.3.x or higher

## How to Use

### 1. Set up the project

To get started, you need to install the dependencies and initialize the project with Taqueria. To do this, run the following commands:
```shell
npm install
```
```
taq init
```

### 2. Add faucet keys
 
You will need to add faucet keys for whichever network you want to use. To do this, visit [teztnets.xys](https://teztnets.xys) and obtain a faucet file. Then copy the JSON contents of the file into the `facuet` property of the network you wish to use in `./.taq/config.json`:

```json
    "network": {
        "ithaca_network": {
            "label": "Ghostnet Testnet",
            "rpcUrl": "https://ghostnet.ecadinfra.com",
            "protocol": "PtJakart2xVj7pYXJBXrqHgd82rdkLey5ZeeGwDgPp9rhQUbSqY",
            "faucet": {  }
        }
    }
```