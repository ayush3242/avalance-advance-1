## README

### Overview

This repository contains two smart contracts: an ERC-20 token contract and a Vault contract. The ERC-20 contract implements a standard token, while the Vault contract allows users to deposit and withdraw these tokens in exchange for shares.

### ERC-20 Token Contract

The ERC-20 contract follows the standard interface for ERC-20 tokens, providing basic functionalities like transferring tokens and managing allowances.

**Key Functions:**
- `totalSupply()`: Returns the total number of tokens in existence.
- `balanceOf(address account)`: Provides the token balance of a given address.
- `transfer(address recipient, uint amount)`: Transfers tokens from the caller's account to a recipient.
- `allowance(address owner, address spender)`: Checks the remaining tokens that a spender is allowed to transfer on behalf of the owner.
- `approve(address spender, uint amount)`: Allows a spender to transfer up to a certain number of tokens from the caller's account.
- `transferFrom(address sender, address recipient, uint amount)`: Transfers tokens from one account to another using an allowance.

**Events:**
- `Transfer`: Emitted when tokens are moved from one account to another.
- `Approval`: Emitted when an allowance is set by calling `approve`.

### Vault Contract

The Vault contract enables users to deposit ERC-20 tokens and receive shares in return. Users can also withdraw their tokens by redeeming their shares.

**Key Functions:**
- `constructor(address _token)`: Initializes the Vault with a specific ERC-20 token.
- `deposit(uint _amount)`: Allows users to deposit tokens into the Vault. The Vault mints shares based on the deposit amount relative to the total supply and Vault's balance.
- `withdraw(uint _shares)`: Allows users to withdraw their tokens by burning their shares. The amount of tokens received is proportional to the shares redeemed.

**Internal Functions:**
- `_mint(address _to, uint _shares)`: Mints shares for a user.
- `_burn(address _from, uint _shares)`: Burns shares from a user.

### License

This project is licensed under the MIT License. See the LICENSE file for details.

---

This concise README provides a quick overview of the ERC-20 and Vault contracts. For more detailed information, refer to the source code and comments within the contracts.
