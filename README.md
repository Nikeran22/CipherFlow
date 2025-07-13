# CipherFlow: Automated Zero-Knowledge Faucet Interaction

CipherFlow automates interaction with zero-knowledge token faucets, enabling scripting for USDZ/cUSDZ transfers, on-chain decryption via a shielded testnet, and automated Zama Guild completion. This project streamlines the process of acquiring and utilizing confidential tokens for testing and development purposes within zero-knowledge environments.

CipherFlow addresses the inherent complexities and time-consuming nature of manually interacting with zero-knowledge faucets. Developers often face challenges in consistently obtaining testnet tokens and navigating the intricacies of shielded testnets. This project abstracts away these complexities, providing a simple, configurable interface for automating the entire process. By scripting token transfers, decrypting transactions on-chain, and automating guild completion tasks, CipherFlow significantly reduces the overhead associated with developing and testing confidential applications.

The core benefit of CipherFlow lies in its ability to accelerate the development lifecycle for zero-knowledge applications. It eliminates the need for manual intervention in acquiring testnet tokens, allowing developers to focus on building and iterating on their core product. The automated decryption and guild completion features further enhance efficiency by streamlining the tasks required to fully utilize these testnet tokens. CipherFlow empowers developers to rapidly prototype, test, and deploy confidential applications with minimal friction.

## Key Features

*   **Automated Faucet Interaction:** Scripts the process of requesting USDZ/cUSDZ tokens from designated testnet faucets. This includes handling rate limiting, solving captchas (if necessary), and managing multiple accounts for increased throughput. The implementation uses a modular approach allowing for easy addition of support for new faucets.
*   **Configurable Token Transfer:** Allows specifying the desired amount of tokens to transfer, the recipient address, and any associated gas limits. The transfer logic leverages the underlying zero-knowledge protocol to ensure privacy and confidentiality. Example: `transferToken('0x123...', 100, {gasLimit: 21000})`
*   **On-Chain Decryption:** Automates the process of decrypting transaction outputs on the shielded testnet. This involves submitting decryption keys and proofs to a smart contract, enabling the recipient to access the transferred tokens. The decryption process uses the `ethers.js` library to interact with the smart contract.
*   **Zama Guild Completion:** Automates tasks required to complete the Zama Guild challenges, such as claiming roles and verifying token ownership. This feature ensures that developers can seamlessly participate in the Zama ecosystem and access its resources. It uses the Discord API and the Zama Guild API for automation.
*   **Account Management:** Provides a secure and efficient way to manage multiple Ethereum accounts. This includes generating new accounts, importing existing accounts via private keys, and storing account information securely. The account data is stored in an encrypted file using a strong encryption algorithm.
*   **Customizable Configuration:** Allows fine-grained control over various parameters, such as faucet endpoints, gas prices, and decryption settings. These parameters can be configured via environment variables or a configuration file.
*   **Error Handling and Logging:** Implements robust error handling and logging mechanisms to ensure that the process runs smoothly and any issues are promptly identified and resolved. All relevant events are logged to a file for debugging and analysis.

## Technology Stack

*   **TypeScript:** Provides static typing, improved code maintainability, and enhanced developer productivity. Used as the primary language for the project.
*   **ethers.js:** A comprehensive Ethereum library for interacting with smart contracts and the Ethereum blockchain. Used for token transfers, decryption, and other on-chain operations.
*   **dotenv:** Loads environment variables from a `.env` file, allowing for easy configuration of sensitive information.
*   **Node.js:** A JavaScript runtime environment that allows for executing JavaScript code server-side.
*   **Zama Shielded Testnet:** The specific testnet where the tokens are transferred and decrypted.
*   **Discord.js**: A powerful Node.js module for interacting with the Discord API. Used for Zama Guild completion.

## Installation

1.  **Clone the repository:**
    `git clone https://github.com/Nikeran22/CipherFlow.git`

2.  **Navigate to the project directory:**
    `cd CipherFlow`

3.  **Install dependencies:**
    `npm install`

4.  **Install Zokrates (if needed for specific Zama functionality):**
    Follow the instructions on the Zokrates website: [https://zokrates.github.io/](https://zokrates.github.io/)

## Configuration

1.  **Create a `.env` file in the project root directory.**

2.  **Define the following environment variables:**

    *   `PRIVATE_KEY`: The private key of the Ethereum account you will use to interact with the faucet and shielded testnet.
    *   `FAUCET_ENDPOINT`: The URL of the USDZ/cUSDZ faucet.
    *   `DECRYPTION_CONTRACT_ADDRESS`: The address of the smart contract responsible for decryption on the shielded testnet.
    *   `DISCORD_BOT_TOKEN`: The Discord bot token required for automating the Zama Guild Completion process.
    *   `GUILD_ID`: The ID of the Zama Guild Discord server.
    *   `RPC_URL`: The RPC URL of the shielded testnet. For example, `https://goerli.infura.io/v3/<YOUR_INFURA_PROJECT_ID>`.
    *   `GAS_PRICE`: (Optional) The gas price to use for transactions. If not specified, the default gas price will be used.

Example `.env` file:

PRIVATE_KEY=0x...
FAUCET_ENDPOINT=https://example.com/faucet
DECRYPTION_CONTRACT_ADDRESS=0x...
DISCORD_BOT_TOKEN=YOUR_DISCORD_BOT_TOKEN
GUILD_ID=1234567890
RPC_URL=https://goerli.infura.io/v3/<YOUR_INFURA_PROJECT_ID>

## Usage

1.  **Run the main script:**
    `npm run start`

This will initiate the automated faucet interaction, token transfer, decryption, and guild completion process. You can customize the behavior of the script by modifying the configuration parameters and the script's code.

Example: To transfer 100 USDZ tokens to address 0x1234567890123456789012345678901234567890, use this code snippet inside your script:

import { transferToken } from './utils/tokenTransfer';

async function main() {
  await transferToken('0x1234567890123456789012345678901234567890', 100);
}

main();

The `transferToken` function handles the intricacies of creating and sending a transaction to the shielded testnet.
You can consult the documentation for each function in the `./utils` directory for more detailed information.

## Contributing

We welcome contributions to CipherFlow! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise code with thorough documentation.
4.  Submit a pull request with a detailed description of your changes.
5.  Ensure that all tests pass before submitting your pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/Nikeran22/CipherFlow/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the Zama team for their contributions to zero-knowledge cryptography and the development of the shielded testnet. Their work has made this project possible.