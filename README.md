<img width="1175" height="295" alt="image" src="https://github.com/user-attachments/assets/4ff04eda-1550-4a2a-a312-2c38e0c27ecb" />

Link: https://stellar.expert/explorer/testnet/contract/CDAMWYX2M6GUUJWJR4DRK7OR5AI4S2SGCBMEFZ6WZUFHCJPRVNZFJWA6

Contract ID = CDAMWYX2M6GUUJWJR4DRK7OR5AI4S2SGCBMEFZ6WZUFHCJPRVNZFJWA6

Project Title: Stellar Ingame Trading

Project Description: Gamers purchase in-game items that they use for trading, selling, and other activities; however, 
this system is often exploited by scammers who deceive players, steal items, or carry out fraudulent trades due to the 
lack of secure and trustless transaction methods. By using Stellar and Soroban smart contracts, in-game item 
trading becomes secure and automated, eliminating the risks of trust-based transactions and protecting players from scams.

Project Vision: The project aims to create a secure and decentralized gaming ecosystem where players truly own their 
in-game items and can trade them safely using Stellar and Soroban smart contracts, eliminating scams and enabling trustless, 
transparent transactions.

Deployed Smart Contract Details:

lib.rs

●	Full Soroban smart contract in Rust

●	All necessary imports from soroban-sdk

● Contract struct, storage keys, and public functions covering: NFT item minting (with ownership), secure trading and transfer of in-game items, duplicate or fraud detection, transaction verification, and XLM-based payments or rewards

●	Inline comments explaining what each function does and why



test.rs

●	Exactly 3 tests using soroban_sdk::testutils — no more, no less

●	Test 1 (Happy path): A certificate is successfully registered and the student receives an XLM reward

●	Test 2 (Edge case): A duplicate certificate registration is rejected with the correct error

●	Test 3 (State verification): Contract storage correctly reflects the certificate owner and hash after a successful registration

●	Uses #[cfg(test)] and mod tests structure with Env::default() for all environment setup




Cargo.toml

●	Package name: gaming (snake_case), edition = "2021"

●	soroban-sdk with features = ["testutils"] under [dev-dependencies]

●	[lib] section with crate-type = ["cdylib", "rlib"]

●	[gaming.release] optimized for Wasm output




README.md

●	Stellar features used

●	Prerequisites: Rust toolchain, Soroban CLI version

●	Build instructions: soroban contract build

●	Test instructions: cargo test

●	Testnet deploy: soroban contract deploy

●	Sample CLI invocation calling the certificate registration function with dummy arguments

●	UID License section



Future Scope:

● Add a secure in-game marketplace for buying and selling items

● Allow items to be used across different games

● Improve systems to prevent scams and fraud

● Add play-to-earn rewards for players

● Enable renting of in-game items
