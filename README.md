# CipherFlow: Streamlined Cryptographic Operations

CipherFlow is a TypeScript library designed to provide a composable and type-safe interface for performing common cryptographic operations. It aims to simplify the integration of cryptographic functionality into modern JavaScript and TypeScript applications, reducing the boilerplate and complexity often associated with lower-level cryptographic APIs.

This library focuses on providing a modular architecture that allows developers to select and combine different cryptographic primitives and algorithms without needing to delve into the intricacies of their underlying implementations. CipherFlow offers a high degree of flexibility, enabling developers to construct custom cryptographic workflows tailored to their specific security requirements. By abstracting away the low-level details, CipherFlow promotes secure coding practices and reduces the risk of common cryptographic errors.

CipherFlow prioritizes performance and security. It leverages optimized implementations of cryptographic algorithms whenever possible and includes safeguards against common vulnerabilities such as padding oracle attacks. The library is thoroughly tested and regularly audited to ensure the integrity and reliability of its cryptographic operations. Furthermore, the type-safe nature of TypeScript enhances the overall security posture by catching type-related errors early in the development cycle.

The primary goal of CipherFlow is to empower developers to easily incorporate robust cryptographic functionality into their applications, fostering a more secure and resilient digital landscape. By providing a clear and concise API, CipherFlow lowers the barrier to entry for developers who are new to cryptography, enabling them to implement secure solutions without requiring extensive prior knowledge. It also provides experienced cryptographers with a powerful and flexible tool for building complex cryptographic systems.

## Key Features

*   **Composable Cryptographic Primitives:** Provides a set of independent functions for various cryptographic operations, such as encryption, decryption, hashing, and signing, that can be easily combined to create custom workflows. Example: you can chain an AES encryption function with a SHA-256 hashing function to encrypt data and then generate a hash of the encrypted data.
*   **Type-Safe API:** Leverages TypeScript's strong typing system to prevent common errors related to data types and argument mismatches, improving code reliability and reducing the risk of vulnerabilities. All functions are annotated with comprehensive type definitions to ensure correct usage.
*   **Modular Architecture:** Designed with a modular architecture that allows developers to selectively import only the cryptographic algorithms and primitives they need, minimizing the bundle size and improving application performance. Each module is self-contained and has minimal dependencies.
*   **Support for Multiple Algorithms:** Includes implementations of various cryptographic algorithms, such as AES, RSA, SHA-256, and HMAC, providing flexibility in choosing the most appropriate algorithm for specific security requirements. The specific implementations used are based on the `crypto` module of Node.js and Web Cryptography API for browser support.
*   **Built-in Error Handling:** Incorporates robust error handling mechanisms to gracefully handle exceptions and provide informative error messages, simplifying debugging and improving application resilience. All cryptographic operations include extensive validation to prevent misuse and potential security issues.
*   **Secure Defaults:** Configured with secure default settings to minimize the risk of common cryptographic vulnerabilities, such as weak key sizes or insecure modes of operation. These defaults can be overridden if necessary, but the library encourages the use of secure configurations.

## Technology Stack

*   **TypeScript:** The primary programming language, providing strong typing and improved code organization. TypeScript's type system helps prevent errors and enhances code maintainability.
*   **Node.js:** Used for server-side development and testing. Node.js provides a robust environment for running JavaScript code and accessing system resources.
*   **Web Crypto API:** Leveraged for browser-based cryptographic operations, ensuring cross-platform compatibility. The Web Crypto API provides a standardized interface for accessing cryptographic functionality in web browsers.
*   **ESLint:** Used for linting the code and enforcing coding standards. ESLint helps maintain code consistency and prevent common errors.
*   **Jest:** Used for unit testing the library and ensuring code quality. Jest provides a simple and efficient way to write and run tests.

## Installation

1.  Install Node.js and npm (Node Package Manager) if you haven't already.
2.  Clone the CipherFlow repository from GitHub:

    `git clone https://github.com/Nikeran22/CipherFlow.git`
3.  Navigate to the CipherFlow directory:

    `cd CipherFlow`
4.  Install the dependencies using npm:

    `npm install`

## Configuration

CipherFlow does not rely heavily on external configuration. However, you can customize the behavior of certain cryptographic operations by setting environment variables or passing configuration options directly to the functions. For example:

*   `CIPHERFLOW_LOG_LEVEL`: Set the logging level for debugging purposes (e.g., `DEBUG`, `INFO`, `WARN`, `ERROR`). This variable controls the verbosity of the library's internal logging.

You can also configure specific algorithms by passing options to the corresponding functions. For example, when using AES encryption, you can specify the key size and initialization vector (IV) as options.

## Usage

Example Usage (AES Encryption):



API Documentation:

*   `aesEncrypt(plaintext: string, key: string, iv: string): string`: Encrypts the given plaintext using AES with the provided key and initialization vector. Returns the ciphertext as a string.
*   `aesDecrypt(ciphertext: string, key: string, iv: string): string`: Decrypts the given ciphertext using AES with the provided key and initialization vector. Returns the plaintext as a string.
*   `sha256Hash(data: string): string`: Generates a SHA-256 hash of the given data. Returns the hash as a hexadecimal string.
*   `hmac(data: string, key: string): string`: Generates an HMAC (Hash-based Message Authentication Code) of the given data using the provided key. Returns the HMAC as a hexadecimal string.

## Contributing

We welcome contributions to CipherFlow! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Write clear and concise code with comprehensive unit tests.
4.  Submit a pull request with a detailed description of your changes.
5.  Ensure that all tests pass before submitting your pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/Nikeran22/CipherFlow/blob/main/LICENSE) file for details.

## Acknowledgements

We would like to thank the open-source community for their contributions to the cryptographic algorithms and libraries that CipherFlow relies upon.