---

layout: col-sidebar
title: OWASP Solana Top 10
tags: Solana
level: 2
type: 

---

<div class="alert">
  <p style="text-align:center">
    Work in progress. Follow us on 
    <a href="https://twitter.com/SolanaTop10">X (formerly Twitter)</a> for updates.
  </p>
</div>

### About the Solana Top 10
The OWASP Solana Top 10 is a standard awareness document that intends to provide Solana developers and security teams with insight into the top 10 vulnerabilities found in Solana programs (aka smart contracts). 

### Top 10
* S01:2023 - Integer Overflows and Underflows
* S02:2023 - Missing System Account Check
* S03:2023 - Lack of Error Handling
* S04:2023 - PDA Substitution Check
* S05:2023 - Panic Due to Division by Zero
* S06:2023 - Account Initialized Check
* S07:2023 - Loss of Precision
* S08:2023 - Concurrent State Manipulation
* S09:2023 - Lack of Signature Validation
* S10:2023 - Missing Check for Lamports

### Overview

| Title | Description |
| -- | -- |
| S01 - Integer Overflows and Underflows | Integer overflows and underflows occur in Rust when arithmetic operations exceed the storage limits of a variable's type, leading to unexpected wraparound. Rust's fixed-size integers cannot inherently prevent this, but using checked arithmetic functions (`checked_add`, `checked_sub`, `checked_div`, `checked_mul`) helps avoid these issues by returning a `None` value for operations that would overflow or underflow, allowing for safer error handling and preventing potentially exploitable conditions in Solana smart contracts.|
| S02 - Missing System Account Check | The Missing System Account Check vulnerability in Solana smart contracts arises when contracts interact with sysvar accounts without verifying their authenticity. Sysvar accounts provide essential blockchain data, like timestamps or fee parameters. Attackers might mimic these accounts, leading to misinformation or exploitation. To mitigate this, developers should hardcode the expected sysvar account public keys in their contracts and validate these keys before interacting with the accounts. This ensures the contract only uses legitimate sysvar data, safeguarding against manipulations. |
| S03 - Lack of Error Handling | The "Lack of Error Handling" vulnerability in Solana smart contracts occurs when functions that can return errors are called without checking these errors. This oversight can lead to unintended consequences, as failed operations might not be caught, potentially causing logic flaws or security vulnerabilities in the contract's execution. Properly handling errors, such as by using Rust's `?` operator to propagate errors, ensures that contracts behave predictably and securely, even in the face of unexpected conditions. |
| S04 - PDA Substitution Check | The vulnerability concerns the risk of using a Program Derived Address (PDA) that has not been properly verified, potentially allowing unauthorized actions. PDAs, integral to Solana's programming model, should be securely generated and checked to ensure they correspond to the intended program, preventing misuse by unofficial sources. It's recommended to create PDAs with unique, well-defined criteria, typically tied to an initial configuration, to safeguard against substitution and ensure secure operations within smart contracts. |
| S05 - Panic Due to Division by Zero | The vulnerability highlights a critical issue in Rust programming for Solana smart contracts. When division by zero occurs, Rust panics and terminates the program, potentially destabilizing the system. To mitigate this, it's recommended to always check if the divisor is zero before performing division operations, ensuring the program's stability and preventing unintended terminations. This precaution is vital for maintaining the reliability and security of smart contracts on the Solana blockchain. |
| S06 - Account Initialized Check | The vulnerability occurs when Solana smart contracts fail to verify whether an account has already been initialized, potentially allowing attackers to reinitialize accounts with arbitrary data. To mitigate this risk, contracts should implement checks to ensure accounts are only initialized once, typically by setting and verifying a flag within the account's data. This approach prevents unauthorized reinitialization and secures the contract against such exploits. |
| S07 - Loss of Precision | The vulnerability refers to inaccuracies that occur when rounding operations, like `try_round_u64()`, are used in financial calculations within Solana smart contracts. This can lead to arbitrage opportunities. The recommendation is to use `try_floor_u64()` for rounding, as it prevents the inadvertent addition of extra value, thus reducing the risk of unintended financial discrepancies. |
| S08 - Concurrent State Manipulation | The vulnerability arises when multiple transactions simultaneously interact with the same state in a smart contract without proper synchronization mechanisms. This can lead to inconsistent state changes, race conditions, and potentially exploitable conditions for attackers, especially in high-throughput environments like Solana. To mitigate this risk, contracts should implement locking mechanisms or ensure atomic operations to maintain consistent states across transactions. |
| S09 - Lack of Signature Validation | The vulnerability occurs when a Solana smart contract fails to verify that an operation has been authorized by the rightful account holder, often neglecting to check if a transaction is signed by the required parties. This oversight can allow unauthorized users to execute functions meant for specific roles, leading to security breaches. To mitigate this risk, it's crucial to validate signatures for all sensitive operations, ensuring that actions are executed only by parties with the proper authorization. |
| S10 - Missing Check for Lamports | The vulnerability arises when Solana contracts don't verify an account's lamport balance before reading its data. This oversight can lead to issues since the data remains accessible until the transaction completes, even if an account's balance is zero. To mitigate this risk, ensure to check that an account's lamport balance is greater than zero before proceeding with logic dependent on the account's data, enhancing safety and preventing potential accidents or exploits related to prematurely accessed or manipulated account data. |
