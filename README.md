# Capstone-RealEstate Marketplace
### Capstone Realestate Marketplace DAPP developed using Blockchain Technology

Final project for Blockchain NanoDegree that necessitates the creation of own tokens to represent property titles. Before minting the token, the owner must confirm that she or he is the rightful owner of the property. A zk-SNARKs (zoKrates) technique will be utilized to develop a verification system that can confirm property ownership without revealing any specific information about the property - <b>Zero knowledge proof technique</b>. The token will be listed on a blockchain market place (OpenSea) for others to buy once it has been confirmed.

### Truffle Suite Version

![Activity diagram](/images/truff-Ver01.png)

```
    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ node -v
    v16.14.2
    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ npm -v
    8.11.0
    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ npm i ganache-cli -g
    changed 6 packages, and audited 102 packages in 2s

    2 packages are looking for funding
    run `npm fund` for details

    3 vulnerabilities (1 moderate, 2 high)

    To address all issues, run:
    npm audit fix

    Run `npm audit` for details.
    
    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ npm i truffle -g
```
### Installing development Environment

```
    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ npm install
    
    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ ganache-cli

    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ cd eth-contracts
    
    ┌──(capstone㉿kali)-[~/workspace/Capstone-RealEstate]
    └─$ truffle compile
```
### Run Test and Compile

![Activity diagram](/images/truffle-dev-01.png)

### All 36 tests should pass.

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
```
 Replacing 'Verifier'
   --------------------
   > transaction hash:    0xd411fea17dbbfbba5950de446b8bd76e901a3a49e986b5aafc2e96f66a596357
   > Blocks: 0            Seconds: 12
   > contract address:    0xdC14Ae2D374Db33BD020bE96d43e60ffa1907E46
   > block number:        10807274
   > block timestamp:     1654556431
   > account:             0xBb108964af881f000EE929bde6881D29a244Ee9B
   > balance:             1.884191197538675457
   > gas used:            1444934 (0x160c46)
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.01444934 ETH

```

![Activity diagram](/images/Verifier-01.png)

* [SolnSquareVerifier](https://rinkeby.etherscan.io/tx/0xa921055bc26bcd940f57f766d9be82a776882f9669bb028212a841f5c52d41fa)
```

   Replacing 'SolnSquareVerifier'
   ------------------------------
   > transaction hash:    0xa921055bc26bcd940f57f766d9be82a776882f9669bb028212a841f5c52d41fa
   > Blocks: 1            Seconds: 16
   > contract address:    0x14E49F2Cad0C87D6E734B50C7AF899599Dac6582
   > block number:        10807275
   > block timestamp:     1654556447
   > account:             0xBb108964af881f000EE929bde6881D29a244Ee9B
   > balance:             1.847485977538675457
   > gas used:            3670522 (0x3801fa)
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.03670522 ETH
```

![Activity diagram](/images/SolnSq-01.png)

* [Rinkeby Etherscan](https://rinkeby.etherscan.io/address/0xBb108964af881f000EE929bde6881D29a244Ee9B)

![Activity diagram](/images/RinkebyTrans-01.png)


### OpenSea MarketPlace Storefront link's :

* [Generate OpenSea marketplace](https://opensea.io/collection/collrealestate)
![Activity diagram](/images/opensea01.png)

* [Testnets.opensea.io - Contract Address](https://testnets.opensea.io/0xdC14Ae2D374Db33BD020bE96d43e60ffa1907E46?tab=collected)

*  [Testnets.opensea.io - Minted](https://opensea.io/assets/ethereum/0x495f947276749ce646f68ac8c248420045cb7b5e/84611720491837093809779221035027904948600579508400875676632087296439048208385)
![Activity diagram](/images/opensea-mint01.png)

* [Testnets.opensea.io - 03](https://opensea.io/0xBb108964af881f000EE929bde6881D29a244Ee9B)
![Activity diagram](/images/OS-Cr-01.png)

### OpenSea Token List link's :

https://testnets.opensea.io/collection/ss-erc721mintabletoken-u5ysc3wtyh

[Minted Token - 01](rinkeby.opensea.io/assets/0x14E49F2Cad0C87D6E734B50C7AF899599Dac6582/56)<br>
[Rinkeby Ethscan Token - 01](https://rinkeby.etherscan.io/tx/0xc387c3ab3b4f424d0feb3a1a17cca7276f64f452e163a5556b4389d5e6b95c35)

[Minted Token - 02](rinkeby.opensea.io/assets/0x14E49F2Cad0C87D6E734B50C7AF899599Dac6582/57)<br>
[Rinkeby Ethscan Token - 02](https://rinkeby.etherscan.io/tx/0xdc5d601f4a9f6254a1d53ba0d97d0ec9e2a41d7c1e83ee4893c2e447951d7d5f)

[Minted Token - 03](rinkeby.opensea.io/assets/0x14E49F2Cad0C87D6E734B50C7AF899599Dac6582/58)<br>
[Rinkeby Ethscan Token - 03](https://rinkeby.etherscan.io/tx/0x99170055c3e0189695028a382b74c555e7ca2870b14594601a598125cdcb86c6)

[Minted Token - 04](rinkeby.opensea.io/assets/0x14E49F2Cad0C87D6E734B50C7AF899599Dac6582/59)<br>
[Rinkeby Ethscan Token - 04](https://rinkeby.etherscan.io/tx/0xb043d39ce71cb239b8e6456be167d5e950b8bc7a664c6ade6528fde52a8be23a)

[Minted Token - 05](rinkeby.opensea.io/assets/0x14E49F2Cad0C87D6E734B50C7AF899599Dac6582/60)<br>
[Rinkeby Ethscan Token - 05](https://rinkeby.etherscan.io/tx/0x666e0d41f7a974abd69636acc3989c87f2e83b06e4990e434ce547bd862a38eb)




### Development Libraries and Tools used for this projects 
* [Ethereum](https://www.ethereum.org/) - Ethereum is a decentralized platform that runs smart contracts. The SupplyChain contract is deployed on Rinkeby Test Network
* [Truffle Framework](http://truffleframework.com/) - Truffle is the most popular development framework for Ethereum with a mission to make your life a whole lot easier. Used for development and testing.
* [ganache-cli](https://www.npmjs.com/package/ganache-cli) Ganache CLI, part of the Truffle suite of Ethereum development tools, is the command line version of Ganache. Used to kickstart a a evm and personal blockchain to deploy and test the contract locally.
* [web3js](https://www.npmjs.com/package/web3) Ethereum JavaScript API.
* [truffle-hdwallet-provider](https://www.npmjs.com/package/truffle-hdwallet-provider) - HD Wallet-enabled Web3 provider. Use it to sign transactions for addresses. Used in truffle.cmd for deployment of contracts
* [Visual Studio Code](https://code.visualstudio.com/) - Web editor
* [lite-server](https://www.npmjs.com/search?q=lite-server) - Lightweight development node server for serving a web app. Used to kickstart the http server to deploy the html and js to interract with the dapp.
* [Open Zeppelin ](https://openzeppelin.org/)
* [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)
* [Docker](https://docs.docker.com/install/)
* [ZoKrates](https://github.com/Zokrates/ZoKrates)

# Project Resources

* [Remix - Solidity IDE](https://remix.ethereum.org/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Truffle Framework](https://truffleframework.com/)
* [Ganache - One Click Blockchain](https://truffleframework.com/ganache)
* [Open Zeppelin ](https://openzeppelin.org/)
* [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)
* [Docker](https://docs.docker.com/install/)
* [ZoKrates](https://github.com/Zokrates/ZoKrates)

## Authors

* **Shan PB** - [Shan PB Github](https://github.com/codemonk22)

## License

This project is licensed under the MIT License 





