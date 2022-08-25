# What is a hack?
-Loopholes in the smart contracts due to poor coding which causes functional manipulation

The following are some smart contract hacks: 
Re-Entrancy: 
- Meaning- Invocation of an external function while another function is undergoing without hampering the current function's execution
- Most destructive attacks in the Solidity smart contract
-  A reentrancy attack occurs when a function makes an external call to another untrusted contract. Then the untrusted contract makes a recursive call back to the original function in an attempt to drain funds.
- When the contract fails to update its state before sending funds, the attacker can continuously call the withdraw function to drain the contract’s funds. 
- Example- A famous real-world Reentrancy attack is the DAO attack which caused a loss of 60 million US dollars.

Reentrancy attacks over years-
- Uniswap/Lendf.Me hacks (April 2020) – $25 mln, attacked by a hacker using a reentrancy.
- The BurgerSwap hack (May 2021) – $7.2 million because of a fake token contract and a reentrancy exploit.
- The SURGEBNB hack (August 2021) – $4 million seems to be a reentrancy-based price manipulation attack.
- CREAM FINANCE hack (August 2021) – $18.8 million, reentrancy vulnerability allowed the exploiter for the second borrow.
- Siren protocol hack (September 2021) – $3.5 million, AMM pools were exploited through reentrancy attack.
To prevent a reentrancy attack in a Solidity smart contract, you should:
- Ensure all state changes happen before calling external contracts, i.e., update balances or code internally before calling external code
- Use function modifiers that prevent reentrancy

Arithmetic Overflow and Underflow
- Overflow- variable size exceeding the datatype  byte size
- Underflow- variable size subceeding the datatype  byte size
- The value of the identifier resets if underflow or overflow occurs
Prevention:
- Solidity compiler version 0.8 throws an error for arithmetic overflow and underflow
- Use SafeMath to will prevent arithmetic overflow and underflow

Self Destruct
- The selfdestruct(address)function removes all bytecode from the contract address and sends all ether stored to the specified address. If this specified address is also a contract, no functions (including the fallback) get called
- An attacker can create a contract with a selfdestruct() function, send ether to it, call selfdestruct(target) and force ether to be sent to a target
Prevention:
- This vulnerability arises from the misuse of this.balance. Your contract should avoid being dependent on the exact values of the balance of the contract because it can be artificially manipulated
- If exact values of deposited ether are required, a self-defined variable should be used that gets incremented in payable functions, to safely track the deposited ether. This can prevent your contract to be influenced by the forced ether sent via a selfdestruct() call
  
Accessing Private Data
Anyone using the blockchain explorer can view the private variables
Delegatecall
Source of Randomness
Denial of Service
Phishing with tx.origin
Hiding Malicious Code with External Contract
Honeypot
Front Running
Block Timestamp Manipulation
Signature Replay
Bypass Contract Size Check
