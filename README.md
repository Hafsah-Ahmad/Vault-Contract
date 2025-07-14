                                                                   Vault Smart Contract

A secure and minimal Ethereum smart contract that allows users to deposit and withdraw Ether, with complete tracking of user balances and owner-controlled features.

Overview=

The Vault contract enables:

-  ETH deposits and withdrawals
-  Per-user balance tracking
-  Secure ownership transfer
-  Transparent event logging

 Features=

- Deposit ETH into the vault
- Withdraw your own ETH balance anytime
- View total vault balance
- Transfer contract ownership to another address
- Emits events for deposits, withdrawals, and ownership transfers

 Contract Details=

- Contract Name: Vault
- Language: Solidity ^0.8.0
- License: MIT
- Dependencies: None (no external libraries)

Functions=
Public Functions

- deposit() 
  Deposits ETH into the contract.  
  Requirements: msg.value > 0
  Emits: Deposited(address user, uint amount)

- withdraw(uint amount)  
  Withdraws ETH from the caller's balance.  
  Requirements:  
  - amount > 0
  - balances[msg.sender] >= amount 
  Emits: Withdrawn(address user, uint amount)

- getVaultBalance()
  Returns the total ETH held by the contract.

- balances(address)  
  View the ETH balance of any user.

Owner-Only Function=

- transferOwnership(address newOwner)
  Transfers ownership of the contract to a new address.  
  Requirements: 
  - Caller must be the current owner  
  - newOwner != address(0)
  Emits: OwnershipTransferred(address oldOwner, address newOwner)

 Modifier=
- onlyOwner= 
  Restricts function access to the contract owner.


