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
* S04:2023 - Insecure Randomness Generation
* S05:2023 - Panic Due to Division by Zero
* S06:2023 - Account Initialized Check
* S07:2023 - Loss of Precision
* S08:2023 - Concurrent State Manipulation
* S09:2023 - Lack of Signature Validation
* S10:2023 - Reentrancy Attacks

### Overview

| Title | Description |
| -- | -- |
| S01 - Integer Overflows and Underflows | Integer overflows and underflows occur in Rust when arithmetic operations exceed the storage limits of a variable's type, leading to unexpected wraparound. Rust's fixed-size integers cannot inherently prevent this, but using checked arithmetic functions (`checked_add`, `checked_sub`, `checked_div`, `checked_mul`) helps avoid these issues by returning a `None` value for operations that would overflow or underflow, allowing for safer error handling and preventing potentially exploitable conditions in Solana smart contracts.|
| S02 - Missing System Account Check | The Missing System Account Check vulnerability in Solana smart contracts arises when contracts interact with sysvar accounts without verifying their authenticity. Sysvar accounts provide essential blockchain data, like timestamps or fee parameters. Attackers might mimic these accounts, leading to misinformation or exploitation. To mitigate this, developers should hardcode the expected sysvar account public keys in their contracts and validate these keys before interacting with the accounts. This ensures the contract only uses legitimate sysvar data, safeguarding against manipulations. |
| S03 - Lack of Error Handling | The "Lack of Error Handling" vulnerability in Solana smart contracts occurs when functions that can return errors are called without checking these errors. This oversight can lead to unintended consequences, as failed operations might not be caught, potentially causing logic flaws or security vulnerabilities in the contract's execution. Properly handling errors, such as by using Rust's `?` operator to propagate errors, ensures that contracts behave predictably and securely, even in the face of unexpected conditions. |
| S04 - Insecure Randomness Generation | .. |
| S05 - Panic Due to Division by Zero | .. |
| S06 - Account Initialized Check | .. |
| S07 - Loss of Precision | .. |
| S08 - Concurrent State Manipulation | .. |
| S09 - Lack of Signature Validation | .. |
| S10 - Reentrancy Attacks | .. |
