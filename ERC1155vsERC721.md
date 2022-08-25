## ERC1155 vs ERC721

- ERC-1155 permits the creation of both semi-fungible tokens and non-fungible tokens, whereas ERC-721 permits only the latter.
- In ERC-1155, smart contracts are linked to multiple URIs and do not store additional metadata (such as file names). In comparison, ERC-721 only supports static metadata stored directly on the smart contract for each token ID,, increasing deployment costs and limiting flexibility.
- ERC-1155’s smart contracts support an infinite number of tokens, whereas ERC-721 needs a new smart contract for each type of token.
- ERC-1155 also allows batch transfers of tokens, which can reduce transaction costs and times. With ERC-721, if you want to send multiple tokens, they happen individually.

Key difference:
1. Smart Contract: First, the ERC-721 standard produces NFTs solely and forces developers to create a smart contract for each new token. On the other hand, ERC-1155 allows developers to develop a single smart contract that can be used to mint either fungible tokens or NFTs.
2. Efficiency: Since ERC-721 allows a single operation for each transaction, it is expensive and time-consuming. At the same time, it reduces the effectiveness of the blockchain network with redundant code. Whereas, ERC-1155 allows multiple operations in a single transaction. Therefore, the transactions are cheaper and more efficient. Plus, unlike ERC-721, which utilizes significant space, ERC-1155 uses less storage space on a blockchain network.
