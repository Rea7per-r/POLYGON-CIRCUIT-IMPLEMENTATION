# Hardhat Circom

A [hardhat-circom](https://github.com/projectsophon/hardhat-circom) template to generate zero-knowledge circuits, proofs, and Solidity verifiers. This Hardhat plugin integrates Circom and SnarkJS into your build process, combining the multiple steps of the Circom & SnarkJS workflow into your Hardhat workflow.

## Features

By providing configuration containing your Phase 1 Powers of Tau and circuits, this plugin will:
1. Compile the circuits
2. Apply the final beacon
3. Output your wasm and zkey files
4. Generate and output Verifier contracts

## How to Start

### 1. Install the Plugin

Move to your project directory and run the following command:

```bash
npm install hardhat-circom
```
# Generate Circuit Intermediaries and Verifier Contract
Run the following command to generate the output file with circuit intermediaries and the MultiplierVerifier.sol contract:
```bash
npx hardhat circom
```
# Prove and Deploy
Run the following command to prove and deploy:
```bash
npx hardhat run scripts/deploy.ts
```

This script performs the following actions:

- Deploys the MultiplierVerifier.sol contract
- Generates a proof from circuit intermediaries with generateProof()
- Generates calldata with generateCallData()
- Calls verifyProof() on the verifier contract with calldata
With these commands, you can compile a ZKP, generate a proof, deploy a verifier, and verify the proof 🎉

Custom Circuits
To add a new custom circuit, make sure you make the necessary changes in hardhat.config.ts and circuits.config.json.

Feel free to deploy it on any network, i have deploy it on sepolia testnet.

Author
surajx070@gmail.com
