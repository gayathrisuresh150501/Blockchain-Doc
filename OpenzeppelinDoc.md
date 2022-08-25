# Hooks:
1. Functions that are called before or after some action takes place. They provide a centralized point to hook into and extend the original behavior.
2. _beforeTransferHook is the only available hook in all the ERC token standards.
3. Rules:
-  Whenever you override a parent’s hook, re-apply the virtual attribute to the hook. That will allow child contracts to add more functionality to the hook. 
- Always call the parent’s hook in your override using super. This will make sure all hooks in the inheritance tree are called: contracts like ERC20Pausable rely on this behavior.

Example
contract MyToken is ERC20 {
    function _beforeTokenTransfer(address from, address to, uint256 amount)
        internal virtual override // Add virtual here!
    {
        super._beforeTokenTransfer(from, to, amount); // Call parent hook
        ...
    }
}

EIP - Ethereum Improvement Proposal
