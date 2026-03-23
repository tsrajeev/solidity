# Solidity Hardhat Project

This repository is a sample Hardhat 3 project setup for Ethereum smart contract development.

- Hardhat config: `hardhat.config.ts`
- Solidity contracts: `contracts/Counter.sol`
- Solidity tests: `contracts/Counter.t.sol`
- TypeScript tests: `test/Counter.ts`
- Ignition deployment module: `ignition/modules/Counter.ts`
- Example script: `scripts/send-op-tx.ts`

## Prerequisites

- Node.js LTS (22.x recommended). Hardhat does not support Node 25+ unstable releases.
- npm or pnpm (npm is used in this project by default).

Verify your version:

```bash
node --version
```

## Install dependencies

```bash
npm install
```

## Recommended .gitignore

This repository includes a ready-to-use `.gitignore` for Node/Hardhat artifacts.

## Common Hardhat commands

Compile:

```bash
npx hardhat compile
```

Run all tests:

```bash
npx hardhat test
```

Run only Solidity tests:

```bash
npx hardhat test solidity
```

Run Node.js runner tests:

```bash
npx hardhat test nodejs
```

Run a Hardhat console:

```bash
npx hardhat console
```

## Ignition deployment

Local EDR-simulated deployment:

```bash
npx hardhat ignition deploy ignition/modules/Counter.ts
```

Sepolia deployment:

1. Set network vars (via config variable or CLI):

```bash
# set secret in keystore
npx hardhat keystore set SEPOLIA_PRIVATE_KEY
# set RPC URL in environment or keystore
export SEPOLIA_RPC_URL="https://sepolia.infura.io/v3/<YOUR_KEY>"
```

2. Deploy:

```bash
npx hardhat ignition deploy --network sepolia ignition/modules/Counter.ts
```

## Network config in this project

`hardhat.config.ts` has:

- `hardhatMainnet` (edr-simulated, l1)
- `hardhatOp` (edr-simulated, op)
- `sepolia` (http, l1)

## Notes

- Run `npx hardhat --help` for all available tasks.
- If you see `Error HHE3: No Hardhat config file found`, ensure you are in the repo root and that `hardhat.config.ts` exists.
- Use Node 22 LTS to avoid hardhat compatibility warnings.

