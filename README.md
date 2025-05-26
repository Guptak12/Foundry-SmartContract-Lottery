# Foundry Smart Contract Lottery

![Foundry](https://img.shields.io/badge/Built%20with-Foundry-FFDB1C.svg?style=flat-square)
![Solidity](https://img.shields.io/badge/Solidity-%3E%3D0.8.4-363636.svg?style=flat-square&logo=solidity)

A decentralized lottery system built with Foundry, implementing a secure and transparent on-chain lottery mechanism.

## Features

- **Chainlink VRF**: Verifiable random number generation for fair winner selection
- **Automated Draws**: Time-based lottery rounds with automatic winner selection
- **Player Management**: Secure entry system with ETH requirements
- **Prize Distribution**: Automatic payout to the winner
- **Owner Controls**: Secure admin functions for maintenance

## Prerequisites

- [Foundry](https://getfoundry.sh/) (install via `curl -L https://foundry.paradigm.xyz | bash`)
- Node.js (for optional frontend)
- Basic understanding of Solidity and smart contracts

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Guptak12/Foundry-SmartContract-Lottery.git
   cd Foundry-SmartContract-Lottery
   ```

2. Install dependencies:
   ```bash
   forge install
   ```

3. Set up environment variables:
   ```bash
   cp .env.example .env
   ```
   Fill in your environment variables in the `.env` file.

## Usage

### Testing
Run all tests:
```bash
forge test
```

Run specific tests:
```bash
forge test --match-test testFunctionName
```

### Deployment
To deploy to a network:
```bash
forge script script/DeployLottery.s.sol --rpc-url <RPC_URL> --private-key <PRIVATE_KEY> --broadcast --verify -vvvv
```

### Verification
Verify the contract:
```bash
forge verify-contract <CONTRACT_ADDRESS> src/Lottery.sol:Lottery --chain-id <CHAIN_ID> --verifier-url <VERIFIER_URL> --etherscan-api-key <API_KEY>
```

## Contract Architecture

```
src/
├── Lottery.sol                # Main lottery contract
└── interfaces/
    ├── IVRFCoordinatorV2.sol  # Chainlink VRF interface
    └── IERC20.sol            # ERC20 interface
```

## Security Considerations

- The contract uses Chainlink VRF for provably fair randomness
- All critical functions are protected with appropriate modifiers
- Withdrawal pattern implemented for secure fund management

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
