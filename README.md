# Capstone-RealEstate
Capstone Realestate Marketplace Developed using Blockchain Technology

```
┌──(capstone㉿bcdev05)-[~/workspace/Capstone-RealEstate/eth-contracts]
└─$ truffle develop
This version of µWS is not compatible with your Node.js build:

Error: Cannot find module './uws_linux_arm64_93.node'
Falling back to a NodeJS implementation; performance may be degraded.


Warning: Both truffle-config.js and truffle.js were found. Using truffle-config.js.
Truffle Develop started at http://127.0.0.1:9545/

Accounts:
(0) 0x845c89c446544e9f0d9c40c319ce3a76a7897e86
(1) 0x1b0fce2ca8214c2e30a9390b7a8fdeb17d7cb952
(2) 0x9513f3419ba16f97288da8d5fb6d85d025d0d21a
(3) 0xb5f1dd5ed38975ed938ac7e8c29c78fcce40017d
(4) 0x80bc6f9a6a3f47db9451d723387d4bbfb139f9a5
(5) 0xed1befd597ce56c2fba16728d25ff1a7179cdc3d
(6) 0xe916389148367ea2af0854bede00aee88aa5550d
(7) 0x99491f15e1c54404811fd7a05be4a15ba2726eed
(8) 0x4cc64c0603c6b7fe2f6bdac0dafc1712eb69e0a8
(9) 0xb761aea1ec97dd12c157b81b6b45a84d1b3d4d30

Private Keys:
(0) a37ec4f9d56d4d28fa017c780477f4e179b754e2bed1be8af04e52119e4663f1
(1) a413663e678a4ba3f28034004561ae5a6c7be5c3221e75410795d0f6673bc07e
(2) 83413e5d3b85d59fa43497ad53a54d871a469de12b7677da4ecc6b7c32aa4543
(3) de21728ce56244c00d7d3705bbde95898a93543de8836a40bd22544806d1c59c
(4) a35f44bfe9618395eeaced191a5b20427286095c6d210d3d2b94f1fbeda59654
(5) f2376cbedcf111cd17144645700b3c58f3e928d1bd5d53eb20fcb2d5cbd0cf9b
(6) 6453233cda47a5aa8dc04169a8e0c26b9cc21a06934996432f689eed9afe688c
(7) 3b5b6c964129b21a844cbc9b6916d9c09023587b005e52e6bea91d3557b4b753
(8) 9b5eb23e0ad63ac73b96f4b357bb7f20d198a0271e0fcfbc3a30dae076524180
(9) 5936473b92d8083e4cf02e352cecdfe8997535a00758bc0db86274cd864712f2

Mnemonic: spray tower cup country between fancy image life tuition nation betray prepare

⚠️  Important ⚠️  : This mnemonic was created for you by Truffle. It is not secure.
Ensure you do not use it on production blockchains, or else you risk losing funds.

truffle(develop)> test
Using network 'develop'.


Compiling your contracts...
===========================
> Compiling ./contracts/ERC721MintableComplete.sol
> Compiling ./contracts/Migrations.sol
> Compiling ./contracts/Oraclize.sol
> Compiling ./contracts/SolnSquareVerifier.sol
> Compiling ./contracts/Verifier.sol
> Compiling openzeppelin-solidity/contracts/drafts/Counters.sol
> Compiling openzeppelin-solidity/contracts/math/SafeMath.sol
> Compiling openzeppelin-solidity/contracts/token/ERC721/IERC721Receiver.sol
> Compiling openzeppelin-solidity/contracts/utils/Address.sol
> Compilation warnings encountered:

    project:/contracts/Oraclize.sol:372:5: Warning: Function state mutability can be restricted to pure
    function __callback(bytes32 _myid, string memory _result, bytes memory _proof) public {
    ^ (Relevant source part starts here and spans across multiple lines).

> Artifacts written to /tmp/test--32633-bExX64ouzy0i
> Compiled successfully using:
   - solc: 0.5.2+commit.1df8f40c.Emscripten.clang


  Contract: ERC721MintableComplete
    Test suite: Ownable inherited
      ✔ should return contract owner
      ✔ should NOT allow unauthorized address to transfer ownership (1136ms)
      ✔ should allow to transfer ownership and emit event (1075ms)
      ✔ should fail when minting when caller is not contract owner (1051ms)
    Test suite: Pausable inherited
      ✔ should NOT allow unauthorized address to pause the contract (1057ms)
      ✔ should NOT allow unauthorized address to unpause the contract (1048ms)
      ✔ should allow owner to pause the contract and emit event (1053ms)
      ✔ should NOT allow owner to pause the contract when contract is already paused (1055ms)
      ✔ should allow owner to unpause the contract and emit event (1059ms)
      ✔ should NOT allow owner to unpause the contract when contract is already unpaused (1076ms)
      ✔ should fail when minting when contract is paused (2090ms)
    Test suite: ERC721Metadata inherited
      ✔ should get the correct token name
      ✔ should get the correct token symbol
      ✔ should get the correct token baseTokenURI
    Test suite: ERC721MintableComplete
      ✔ should not mint an already existent tokenId (1052ms)
      ✔ should not mint to an invalid address 0x0 (1066ms)
      ✔ should return total supply
      ✔ should get token balance
      ✔ should return token uri
      ✔ should return the correct ownerOf for a token
      ✔ should allow the token owner to approve another user for its token (1057ms)
      ✔ should allow approved to transfer token from one owner to another and verify this (1127ms)
      ✔ should allow token owner to transfer token from one owner to another and verify this (1088ms)
      ✔ should NOT allow to transfer to an invalid address 0x0 (1051ms)

  Contract: SolnSquareVerifier
    Test suite: addSolution
      ✔ should NOT allow to addSolution with invalid values or unverifyable solution (2918ms)
      ✔ should allow to add a solution with correct values and emit event (2711ms)
      ✔ should NOT allow to add a solution if the same solution exists already (1059ms)
      ✔ should allow to add more new solutions with correct values and emit event (2736ms)
    Test suite: mintNewNFT
      ✔ should NOT mint a token via mintNewNFT if solution has not been verified (1044ms)
      ✔ should NOT mint a token if solution has been verified on a different account (3785ms)
      ✔ should mint a token if solution is valid, emit events and verify owner and token balance (1102ms)
      ✔ should NOT mint another token if a token for the same solution exists already (1040ms)
      ✔ should mint a NEW token for a NEW valid solution, emit events and verify owner and token balance (3846ms)

  Contract: Verifier
    ✔ should verify true with the correct proof and emit event (13970ms)
    ✔ should verify false with the incorrect proof and not emit event (2325ms)
    ✔ should verify false with the incorrect proof for the input and not emit event (10632ms)


  36 passing (1m)

truffle(develop)> 


```


![Activity diagram](/images/truffle-dev-01.png)
![Activity diagram](/images/truffle-dev-02.png)

```
┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/eth-contracts]
└─$ truffle migrate --network rinkeby --reset
```


![Activity diagram](/images/rink-01.png)
![Activity diagram](/images/rink-02.png)

- [ ] Implement Zokrates
- [ ] Using Docker to install and instantiate a Zokrates zkSnarks development environment
- [ ] Completes the Zokrates proof in square.code by adding the variable names in square.code
- [ ] Compile program
- [ ] Trusted setup
- [ ] Compute witness
- [ ] Generate Proof
- [ ] Export Verifier.sol
