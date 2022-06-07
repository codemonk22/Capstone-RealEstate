# Capstone-RealEstate
Capstone Realestate Marketplace Developed using Blockchain Technology

### Truffle Suite Version

![Activity diagram](/images/truff-Ver01.png)

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

### Steps involved in generating the proof from zokrates

- [ ] Implement Zokrates

```
Install docker and download Zokrates docker image for the supporting OS

┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/zokrates]
└─$ sudo apt update
┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/zokrates]
└─$ sudo apt install -y docker.io
┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/zokrates]
└─$ sudo systemctl enable docker --now
┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/zokrates]
└─$ sudo usermod -aG docker $USER
```
- [ ] Using Docker to install and instantiate a Zokrates zkSnarks development environment
Run the zokrates docker image 

```
┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/zokrates]
└─$ cd code

┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/zokrates/code]
└─$ docker run -v $(pwd):/home/zokrates/code -ti zokrates/zokrates:0.3.0 /bin/bash
```
- [ ] Completes the Zokrates proof in square.code by adding the variable names in square.code

![Activity diagram](/images/sqr-set01.png)

- [ ] Compile program
```
zokrates@01afa6a493df:~/code$ ~/zokrates compile -i square/square.code
Compiling square/square.code
Compiled program:
def main(private _2,_3):
        _4 = (_2 * _2)
        _5 = (_4 - _3)
        # _6, _7 = Rust::ConditionEq(_5)
        _6 == (_5 * _7)
        _8 = (1 - _6)
        0 == (_8 * _5)
        # _9 = Rust::Identity(_8)
        _10 = (1 - _9)
        _11 = (_9 * 1)
        _12 = (_10 * 0)
        _13 = (_11 + _12)
        return _13
Compiled code written to 'out'
Human readable code to 'out.code'
Number of constraints: 12
```
- [ ] Trusted setup
```
zokrates@01afa6a493df:~/code$ ~/zokrates setup
Performing setup...
def main(private _2,_3):
        _4 = (_2 * _2)
        _5 = (_4 - _3)
        # _6, _7 = Rust::ConditionEq(_5)
        _6 == (_5 * _7)
        _8 = (1 - _6)
        0 == (_8 * _5)
        # _9 = Rust::Identity(_8)
        _10 = (1 - _9)
        _11 = (_9 * 1)
        _12 = (_10 * 0)
        _13 = (_11 + _12)
        return _13
num variables: 14
num constraints: 10
num inputs: 2
Swap is not beneficial, not performing
* QAP number of variables: 13
* QAP pre degree: 10
* QAP degree: 16
* QAP number of input variables: 2
* G1 window: 5
* G2 window: 1
* G1 elements in PK: 109
* Non-zero G1 elements in PK: 83
* G2 elements in PK: 15
* Non-zero G2 elements in PK: 5
* PK size in bits: 25438
* G1 elements in VK: 4
* G2 elements in VK: 5
* VK size in bits: 3948
        Verification key in Solidity compliant format:{
                vk.A = Pairing.G2Point([0x37363aef34af30e9a3d2d3204d6e3332977e146e0757ef780b5b170f745f32a, 0x2a303662bf32ad719164d2e8cecfbe71aa5c97fbafb8713da4596260648f4fa4], [0x6f5d17baf72d15e9c49ad9a39e01e5260c36b664646e22dbc8b27da6aa77c6, 0x51edc83861f935b2cdcf10d2829615f353730fe206998d41714994dcb7a703f]);
                vk.B = Pairing.G1Point(0x2ac31cba24aa1b132169be0a6b958c523a91f5d8805fce5a3f69aa71becdc073, 0x280346be37e7a0b620a9e5c0196456cbe484f84f9f7f41cefe12ba4886b0b787);
                vk.C = Pairing.G2Point([0x57468dc4fa951f53e0f5a9a9248a24d5699da35d1886d937fc293dbff3d690a, 0xfc84089dd9d72f3f9ded3220737f2c48f4750999f8c5ccd21e9bb09d463e39c], [0x244092854b3d0600918555e8bbf4d4aa7e67acac07f154e6455752a290a6181e, 0x2dba2dc867bd1c5b29cb9f3b779f21e2a2de8c2da22fbe1964bbe529f0d86266]);
                vk.gamma = Pairing.G2Point([0x256ddf53bf3df7ea687c5938d999a1e787d2af8166188284b1c1c7dffde93c95, 0x970695ef5e321af5cd13dd7f2bd847909cf4266c9f6f9ade0a8759ef09ef711], [0x1f4095902b7db53a8a3747c2304b1bf1858d562a94b4b765512c1373adf375a6, 0x23c4c4b54b38d4294d06a8a10d19d52797037b726126359a632396b8fb129561]);
                vk.gammaBeta1 = Pairing.G1Point(0x216b107ab3181984be989c36dee77283a71971bee14f1c3f5f5c122e8a712860, 0x23b4fe1be0914dae9a8f4ad2b1def7eb1cfcbad9f02ffe7ad1679220978ca0b0);
                vk.gammaBeta2 = Pairing.G2Point([0xc479dc7f3614772b3d7bd523b188b4b2f83e37d3c61f6902e27647dd7b83336, 0xe9a87c3c94ae4d47aec8b3f9601a21fd055382e47371d3fb76c6a9e04b7591f], [0x2bedb256834929c490ad2b4635f4e32999297c0edaf9031273561fbd1df50af5, 0x25efeb6b89c9408c1434b59c9a405ca7a8f7b96450d1257b1a4847ea07924a57]);
                vk.Z = Pairing.G2Point([0x1f7b66065285df5ea5f341aea0e037f7502b25d9b31e5fec7a470ce00f6150c3, 0xb311af8c566befd7feb6a7644142c269d85000a6eed83a7fabbd0c5399ca5a2], [0x998625410e58f48d4c7ab8d03a944c150c796c2eb7d8c9a5798ee36dde8e62b, 0xbe9b2917163d4cc57f9c394abba83ab35b3a07757c101087dcd34375599b51f]);
                vk.IC = new Pairing.G1Point[](3);
                vk.IC[0] = Pairing.G1Point(0x1f0b57a89ba320f902e35d94930b6fc7cb18d099c1ea875f62d20ebe2687bd39, 0x2f57f987d1691e7d187670cda92304fc404f306080c94acf1a0b8f85a4549ae6);
                vk.IC[1] = Pairing.G1Point(0xf00512ec957a2dc5195a0f2ebd45870ce4c37b81df0c36fb39762353170a317, 0x1b3261ab2b1cf0b457cc5fe7b3a47d6bf9b8ba69e49cc950d71182eb21cc5ba);
                vk.IC[2] = Pairing.G1Point(0xb22549802c030137ea03e9af30e54d990f4b929f878e7b344765cee855d55f7, 0xc443fee3c35bed35d55b9e0932f201733e6bf60885856c43db2be5423d58b7f);
                }
setup successful: true
zokrates@01afa6a493df:~/code$ 
```
- [ ] Compute witness
```
zokrates@01afa6a493df:~/code$ ~/zokrates compute-witness -a 3 9          
Computing witness for:
def main(private _2,_3):
        _4 = (_2 * _2)
        _5 = (_4 - _3)
        # _6, _7 = Rust::ConditionEq(_5)
        _6 == (_5 * _7)
        _8 = (1 - _6)
        0 == (_8 * _5)
        # _9 = Rust::Identity(_8)
        _10 = (1 - _9)
        _11 = (_9 * 1)
        _12 = (_10 * 0)
        _13 = (_11 + _12)
        return _13

Witness: 

~out_0 1
zokrates@01afa6a493df:~/code$ ls -ltr
total 32
drwxrwxrwx 2     1001     1001 4096 Jun  6 19:45 square
-rw-r--r-- 1 zokrates zokrates  246 Jun  6 19:47 out.code
-rw-r--r-- 1 zokrates zokrates  583 Jun  6 19:47 out
-rw-r--r-- 1 zokrates zokrates   99 Jun  6 19:48 variables.inf
-rw-r--r-- 1 zokrates zokrates 2176 Jun  6 19:48 verification.key
-rw-r--r-- 1 zokrates zokrates 6394 Jun  6 19:48 proving.key
-rw-r--r-- 1 zokrates zokrates   80 Jun  6 19:51 witness
```
- [ ] Generate Proof
```
zokrates@01afa6a493df:~/code$ ~/zokrates generate-proof
Generating proof...
Using Witness: {"_4": 9, "_9": 1, "_5": 0, "_13": 1, "_2": 3, "_3": 9, "_10": 0, "~out_0": 1, "~one": 1, "_7": 1, "_6": 0, "_12": 0, "_11": 1, "_8": 1}
Public inputs: [1, 9, 1]
Private inputs: [3, 9, 0, 1, 0, 1, 1, 0, 1, 0, 1]
* Elements of w skipped: 3 (33.33%)
* Elements of w processed with special addition: 4 (44.44%)
* Elements of w remaining: 2 (22.22%)
* Elements of w skipped: 1 (33.33%)
* Elements of w processed with special addition: 1 (33.33%)
* Elements of w remaining: 1 (33.33%)
* Elements of w skipped: 4 (36.36%)
* Elements of w processed with special addition: 5 (45.45%)
* Elements of w remaining: 2 (18.18%)
* Elements of w skipped: 4 (30.77%)
* Elements of w processed with special addition: 6 (46.15%)
* Elements of w remaining: 3 (23.08%)
* G1 elements in proof: 7
* G2 elements in proof: 1
* Proof size in bits: 2294
Proof:
A = Pairing.G1Point(0x2f47881a565b0201736b230747213cf0b9d1182c1f91446a7b123ae847be28c3, 0x2d744a140a569be02da60e4ebb289cebee18d27c0dda16376106fda44d7dbb5b);
A_p = Pairing.G1Point(0x27541248c9467abb612f305c9c0e1421317582bb689a8a2017524f5b68603f27, 0xe693c9c95a229dd1050f429096b98445a934f28a9a7e324482ecbf3701a7e85);
B = Pairing.G2Point([0xda9be57ff9d931793073df1706d2d3b5aa1929fda6ab701ad5758435533fcad, 0x12327d462644303be3b268ae89b99ec43f4ae8cdc88a5d3c96e7e861f7897b2e], [0x25de16a48d3c864720cf99272c41bde93ad19d75ba1449bb9abf87c6e393dc0e, 0x196f6c8046689756336da064a643e29ae8157918a7113a50952c8902e40025fa]);
B_p = Pairing.G1Point(0x7e4bc9b70c68144ced338508e041499a5ca7f1cdb348202ca4c8a5a9acdf2dc, 0x22ecad74909ef9137c0efbfa30eb9b7fc975f71bc727dfd6ec7e3de23a92d894);
C = Pairing.G1Point(0x2aaf42e9370c539631a1c38243b9caf9fd3896c70bdca6987257e8070ea535cd, 0x3200a38e79dfe4dca1dda8a679f6fc08046a4a5dc14015dbf9cf9717593686b);
C_p = Pairing.G1Point(0xeb9527fbf5c839fbc2303c5d286f2badb63bf94e82ea0b1566e5d5d150d524e, 0x68c151afe2ed95d32a672e62c2581a2ae1031bf9a0c3b17b487da8032542454);
H = Pairing.G1Point(0x108ebec9a7a33b96729fa8bc6299126d9c4fd22ff9334c6434c6917758fe0bbd, 0x16f4cae1e5f50aaf4d6c3adf20f652048ef81003bbe0cdf17c71fbeae8838eb9);
K = Pairing.G1Point(0x37ea9fa6b53eced136fbda820f113ff687a807daf02d10860d446c777df01fb, 0x21fea58f4a07cb7c4f676582286467b127cf5ee71149be0c1309713b3a55e2fd);
generate-proof successful: true
zokrates@01afa6a493df:~/code$ ls -ltrt
total 36
drwxrwxrwx 2     1001     1001 4096 Jun  6 19:45 square
-rw-r--r-- 1 zokrates zokrates  246 Jun  6 19:47 out.code
-rw-r--r-- 1 zokrates zokrates  583 Jun  6 19:47 out
-rw-r--r-- 1 zokrates zokrates   99 Jun  6 19:48 variables.inf
-rw-r--r-- 1 zokrates zokrates 2176 Jun  6 19:48 verification.key
-rw-r--r-- 1 zokrates zokrates 6394 Jun  6 19:48 proving.key
-rw-r--r-- 1 zokrates zokrates   80 Jun  6 19:51 witness
-rw-r--r-- 1 zokrates zokrates 1367 Jun  6 19:51 proof.json
```
- [ ] Export Verifier.sol
```
zokrates@01afa6a493df:~/code$ ~/zokrates export-verifier
Exporting verifier...
Finished exporting verifier.
zokrates@01afa6a493df:~/code$ ls -ltr
total 48
drwxrwxrwx 2     1001     1001  4096 Jun  6 19:45 square
-rw-r--r-- 1 zokrates zokrates   246 Jun  6 19:47 out.code
-rw-r--r-- 1 zokrates zokrates   583 Jun  6 19:47 out
-rw-r--r-- 1 zokrates zokrates    99 Jun  6 19:48 variables.inf
-rw-r--r-- 1 zokrates zokrates  2176 Jun  6 19:48 verification.key
-rw-r--r-- 1 zokrates zokrates  6394 Jun  6 19:48 proving.key
-rw-r--r-- 1 zokrates zokrates    80 Jun  6 19:51 witness
-rw-r--r-- 1 zokrates zokrates  1367 Jun  6 19:51 proof.json
-rw-r--r-- 1 zokrates zokrates 11425 Jun  6 19:52 verifier.sol
zokrates@01afa6a493df:~/code$ 
```

### Rinkeby Network Deployment

```
┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate/eth-contracts]
└─$ truffle migrate --network rinkeby --reset
```


![Activity diagram](/images/rink-01.png)
![Activity diagram](/images/rink-02.png)



Contract Addresses :  

* [Verifier](https://rinkeby.etherscan.io/tx/0xd411fea17dbbfbba5950de446b8bd76e901a3a49e986b5aafc2e96f66a596357)
![Activity diagram](/images/Verifier-01.png)
* [SolnSquareVerifier](https://rinkeby.etherscan.io/tx/0xa921055bc26bcd940f57f766d9be82a776882f9669bb028212a841f5c52d41fa)
![Activity diagram](/images/SolnSq-01.png)
* [Rinkeby Etherscan](https://rinkeby.etherscan.io/address/0xBb108964af881f000EE929bde6881D29a244Ee9B)
![Activity diagram](/images/RinkebyTrans-01.png)

OpenSea MarketPlace Storefront link's :

* [Opensea.io](https://opensea.io/collection/collrealestate)
* [Testnets.opensea.io - 01](https://testnets.opensea.io/0xdC14Ae2D374Db33BD020bE96d43e60ffa1907E46?tab=collected)
*  [Testnets.opensea.io - 02](https://opensea.io/assets/ethereum/0x495f947276749ce646f68ac8c248420045cb7b5e/84611720491837093809779221035027904948600579508400875676632087296439048208385)
* [Testnets.opensea.io - 03](https://opensea.io/0xBb108964af881f000EE929bde6881D29a244Ee9B)



