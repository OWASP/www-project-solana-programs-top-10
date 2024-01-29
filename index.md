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
* S02:2023 - TBD
* S03:2023 - TBD
* S04:2023 - TBD
* S05:2023 - TBD
* S06:2023 - TBD
* S07:2023 - TBD
* S08:2023 - TBD
* S09:2023 - TBD
* S10:2023 - TBD

### Overview

| Title | Description |
| -- | -- |
| S01 - Integer Overflows and Underflows | In Rust, integers have a fixed size, leading to potential overflows or underflows if arithmetic operations exceed their storage limits. This can be mitigated by using Rust's checked arithmetic functions. ```rust
let result = value.checked_add(additional).ok_or(ProgramError::ArithmeticOverflow)?;```
 |
| S02 - TBD | .. |
| S03 - TBD | .. |
| S04 - TBD | .. |
| S05 - TBD | .. |
| S06 - TBD | .. |
| S07 - TBD | .. |
| S08 - TBD | .. |
| S09 - TBD | .. |
| S10 - TBD | .. |
