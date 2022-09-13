# Udacity Blockchain Capstone

At present, property titles are often paper-based, creating opportunities for errors and fraud. Title professionals find defects in 25% of all titles during the transaction process, according to the American Land Title Association.
Any identified defect makes it illegal to transfer a property title to a buyer until it is rectified. This means property owners often incur high legal fees to ensure authenticity and accuracy of their property titles.
Moreover, title fraud poses a risk to homeowners worldwide. US losses associated with title fraud reportedly averaged around $103,000 per case in 2015, compelling many property buyers to purchase title insurance.
These title management issues could potentially be mitigated by using blockchain technology to build immutable digital records of land titles and using blockchain for transparent transactions. This approach could simplify property title management, making it more transparent and helping to reduce the risk of title fraud and the need for additional insurance.
Some companies and governments around the globe have already implemented blockchain technology for the title management process.
Ghanaian blockchain company Bitland has been working on a solution for Ghana, where it is estimated that almost 80% of land is unregistered, according to Forbes. Those that possess unregistered land find it more difficult to prove legal ownership, increasing their exposure to the risk of land seizures or property theft.

Bitland is seeking to create secure digital public records of ownership on its blockchain platform, with the aim of protecting land owners from title fraud. Bitland has expanded to operate in 7 African nations, India, and is also working with Native Americans in the US.
The capstone will build upon the knowledge you have gained in the course in order to build a decentralized housing product as the following:  
- Before mint a token, we need to verify we own the property. 
- We will generate a pre-knowledge proof using zokrates, zk-SNARKs to create a verification system which can prove we have title to the property without revealing that specific information on the property.
- We will be minting our own tokens to represent we title to the properties. 
- Once the token has been verified we will place it on a blockchain market place (OpenSea) for others to purchase.


________________________________________________________________
## Libraries  
Truffle v5.5.16 (core: 5.5.16)  
Ganache v^7.1.0  
Solidity v0.5.16 (solc-js)  
Node v16.14.0  
Web3.js v1.5.3 
________________________________________________________________

Clone this repository:

```
git clone https://github.com/zeil156/Capstone-Real-Estate-Marketplace-Udacity-Project-Submission-.git
```

Change directory to ```eth-contracts``` folder and install all requisite npm packages (as listed in ```package.json```):

```
cd eth-contracts
npm install
```

Launch Ganache:

```
ganache-cli -m "ball special robot grow omit home square country absent release total act"
```

In a separate terminal window, Compile smart contracts:

```
truffle compile
```  
This will create the smart contract artifacts in folder ```build\contracts```.

Migrate smart contracts to the locally running blockchain, ganache-cli:

```
truffle migrate
```

Your terminal should look something like this:

```
Compiling your contracts...
===========================
> Compiling .\contracts\ERC721Mintable.sol
> Compiling .\contracts\Migrations.sol
> Compiling .\contracts\Oraclize.sol
> Compiling .\contracts\SolnSquareVerifier.sol
> Compiling .\contracts\Verifier.sol
> Compiling openzeppelin-solidity\contracts\drafts\Counters.sol
> Compiling openzeppelin-solidity\contracts\math\SafeMath.sol
> Compiling openzeppelin-solidity\contracts\token\ERC721\IERC721Receiver.sol
> Compiling openzeppelin-solidity\contracts\utils\Address.sol
> Compilation warnings encountered:

    project:/contracts/Oraclize.sol:320:7: Warning: Unreachable code.
      _networkID; // silence the warning and remain backwards compatible
      ^--------^
,project:/contracts/Oraclize.sol:373:7: Warning: Unreachable code.
      _myid; _result; _proof; // Silence compiler warnings
      ^--------------------^
,project:/contracts/Oraclize.sol:371:5: Warning: Function state mutability can be restricted to pure
    function __callback(bytes32 _myid, string memory _result, bytes memory _proof) public {
    ^ (Relevant source part starts here and spans across multiple lines).
,project:/contracts/Verifier.sol:449:5: Warning: Function state mutability can be restricted to view
    function addition(G2Point memory p1, G2Point memory p2) internal returns (G2Point memory r) {
    ^ (Relevant source part starts here and spans across multiple lines).

> Artifacts written to C:\Users\mzeil\Desktop\Working Files\CC6 Project Submission\GitClone\Blockchain-Capstone\eth-contracts\build\contracts
> Compiled successfully using:
   - solc: 0.5.16+commit.9c3226ce.Emscripten.clang


Starting migrations...
======================
> Network name:    'development'
> Network id:      5777
> Block gas limit: 6721975 (0x6691b7)


2_deploy_contracts.js
=====================

   Deploying 'Verifier'
   --------------------
   > transaction hash:    0xa1fbc1470a79633de88a9f340d2d6bb72e3336ad5b375f0d3f34d0e0c612d1a1
- Blocks: 0            Seconds: 0
   > Blocks: 0            Seconds: 0
   > contract address:    0x4E690dC924e81CF7eFb7011ECb3acc89a5BB3919
   > block number:        478
   > block timestamp:     1663021385
   > account:             0x3Bb5457d3D9199DF1b82f37ECe0b23b32CF9B7f0
   > balance:             91.78724606
   > gas used:            992479 (0xf24df)
   > gas price:           20 gwei
   > value sent:          0 ETH
   > total cost:          0.01984958 ETH


   Deploying 'SolnSquareVerifier'
   ------------------------------
   > transaction hash:    0x1172fb50095d6bd7985fa03d57f8587c0361605255fdf6f4d78a877d71b1d320
- Blocks: 0            Seconds: 0
   > Blocks: 0            Seconds: 0
   > contract address:    0x330E8000EF201B985c218096c5eCAbD2652b3b92
   > block number:        479
   > block timestamp:     1663021388
   > account:             0x3Bb5457d3D9199DF1b82f37ECe0b23b32CF9B7f0
   > balance:             91.72153536
   > gas used:            3285535 (0x32221f)
   > gas price:           20 gwei
   > value sent:          0 ETH
   > total cost:          0.0657107 ETH

- Saving migration to chain.
   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:          0.08556028 ETH

Summary
=======
> Total deployments:   2
> Final cost:          0.08556028 ETH
``` 
Test smart contracts:

```
truffle test
```

All 10 tests should pass.  Your terminal should look something like this:
```
Using network 'development'.


Compiling your contracts...
===========================
> Compiling .\contracts\ERC721Mintable.sol
> Compiling .\contracts\ERC721Mintable.sol
> Compiling .\contracts\Migrations.sol
> Compiling .\contracts\Oraclize.sol
> Compiling .\contracts\SolnSquareVerifier.sol
> Compiling .\contracts\SquareVerifier.sol
> Compilation warnings encountered:

    project:/contracts/Oraclize.sol:320:7: Warning: Unreachable code.
      _networkID; // silence the warning and remain backwards compatible
      ^--------^
,project:/contracts/Oraclize.sol:373:7: Warning: Unreachable code.
      _myid; _result; _proof; // Silence compiler warnings
      ^--------------------^
,project:/contracts/Oraclize.sol:371:5: Warning: Function state mutability can be restricted to pure
    function __callback(bytes32 _myid, string memory _result, bytes memory _proof) public {
    ^ (Relevant source part starts here and spans across multiple lines).
,project:/contracts/SquareVerifier.sol:449:5: Warning: Function state mutability can be restricted to view
    function addition(G2Point memory p1, G2Point memory p2) internal returns (G2Point memory r) {
    ^ (Relevant source part starts here and spans across multiple lines).

> Artifacts written to C:\Users\mzeil\AppData\Local\Temp\test--11088-ogRFcTGLavQS
> Compiled successfully using:
   - solc: 0.5.16+commit.9c3226ce.Emscripten.clang


  Contract: TestERC721Mintable
    match erc721 spec
      √ should return total supply (1343ms)
      √ should get token balance (478ms)
      √ should return token uri (178ms)
      √ should transfer token from one owner to another (1391ms)
    have ownership properties
      √ should fail when minting when address is not contract owner (1193ms)
      √ should return contract owner (55ms)

  Contract: Test SolnSquareVerifier
    test solnSquareVerifier with proof
      √ if a new solution can be added for contract and token minted - SolnSquareVerifier (3659ms)
      √ if a repeat solution can be added for contract - SolnSquareVerifier (4397ms)

  Contract: Test SquareVerifier
    test verifier with proof
      √ verify with correct proof (862ms)
      √ verify failure with incorrect proof (666ms)


  10 passing (1m)
```

### Migrate smart contracts to rinkeby blockchain:  
```
create .secret file and save in directory 'eth-contracts' that includes only one line which is the mnemonic used for your MetaMask Rinkeby account
```

```
truffle migrate --network rinkeby
```  

```
Compiling your contracts...
===========================
> Compiling .\contracts\ERC721Mintable.sol
> Compiling .\contracts\ERC721Mintable.sol
> Compiling .\contracts\Migrations.sol
> Compiling .\contracts\Oraclize.sol
> Compiling .\contracts\SolnSquareVerifier.sol
> Compiling .\contracts\SquareVerifier.sol
> Compilation warnings encountered:

    project:/contracts/Oraclize.sol:320:7: Warning: Unreachable code.
      _networkID; // silence the warning and remain backwards compatible
      ^--------^
,project:/contracts/Oraclize.sol:373:7: Warning: Unreachable code.
      _myid; _result; _proof; // Silence compiler warnings
      ^--------------------^
,project:/contracts/Oraclize.sol:371:5: Warning: Function state mutability can be restricted to pure
    function __callback(bytes32 _myid, string memory _result, bytes memory _proof) public {
    ^ (Relevant source part starts here and spans across multiple lines).
,project:/contracts/SquareVerifier.sol:449:5: Warning: Function state mutability can be restricted to view
    function addition(G2Point memory p1, G2Point memory p2) internal returns (G2Point memory r) {
    ^ (Relevant source part starts here and spans across multiple lines).

> Artifacts written to C:\Users\mzeil\Desktop\Working Files\CC6 Project Submission\GitClone\Blockchain-Capstone\eth-contracts\build\contracts
> Compiled successfully using:
   - solc: 0.5.16+commit.9c3226ce.Emscripten.clang


Migrations dry-run (simulation)
===============================
> Network name:    'rinkeby-fork'
> Network id:      4
> Block gas limit: 29970705 (0x1c95111)


1_initial_migration.js
======================

   Deploying 'Migrations'
   ----------------------
   > block number:        11370149
   > block timestamp:     1663027362
   > account:             0x53aA0a0221a5Ea932Be1909E646d1f86491F2330
   > balance:             0.199433657498414241
   > gas used:            226537 (0x374e9)
   > gas price:           2.500000007 gwei
   > value sent:          0 ETH
   > total cost:          0.000566342501585759 ETH

   -------------------------------------
   > Total cost:     0.000566342501585759 ETH


2_deploy_contracts.js
=====================

   Deploying 'SquareVerifier'
   --------------------------
   > block number:        11370151
   > block timestamp:     1663027363
   > account:             0x53aA0a0221a5Ea932Be1909E646d1f86491F2330
   > balance:             0.196838052491146547
   > gas used:            992479 (0xf24df)
   > gas price:           2.500000007 gwei
   > value sent:          0 ETH
   > total cost:          0.002481197506947353 ETH


   Deploying 'SolnSquareVerifier'
   ------------------------------
   > block number:        11370152
   > block timestamp:     1663027367
   > account:             0x53aA0a0221a5Ea932Be1909E646d1f86491F2330
   > balance:             0.188791007468614821
   > gas used:            3218818 (0x311d82)
   > gas price:           2.500000007 gwei
   > value sent:          0 ETH
   > total cost:          0.008047045022531726 ETH

   -------------------------------------
   > Total cost:     0.010528242529479079 ETH

Summary
=======
> Total deployments:   3
> Final cost:          0.011094585031064838 ETH




Starting migrations...
======================
> Network name:    'rinkeby'
> Network id:      4
> Block gas limit: 29999972 (0x1c9c364)


1_initial_migration.js
======================

   Deploying 'Migrations'
   ----------------------
   > transaction hash:    0xf325c065c9ad16ef4e025d4b1dddf7b8b692e33aa12bc3ce04162daea21bae45
- Blocks: 0            Seconds: 0
- Blocks: 0            Seconds: 4
- Blocks: 1            Seconds: 8
   > Blocks: 1            Seconds: 8
   > contract address:    0x209220f07AEFE00496Bee142f6ddb1Caf8CD7948
   > block number:        11370154
   > block timestamp:     1663027369
   > account:             0x53aA0a0221a5Ea932Be1909E646d1f86491F2330
   > balance:             0.209660194498187704
   > gas used:            226537 (0x374e9)
   > gas price:           1.500000008 gwei
   > value sent:          0 ETH
   > total cost:          0.000339805501812296 ETH

- Saving migration to chain.
   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:     0.000339805501812296 ETH


2_deploy_contracts.js
=====================

   Deploying 'SquareVerifier'
   --------------------------
   > transaction hash:    0xd4a63c553c5c938592e31672fca8c5d259003b0ea169e9b37a351dc91dbcff02
- Blocks: 0            Seconds: 0
- Blocks: 0            Seconds: 4
- Blocks: 0            Seconds: 8
- Blocks: 1            Seconds: 12
   > Blocks: 1            Seconds: 12
   > contract address:    0xD27F53208FBbeB58bE9f7143Adff02026800B66a
   > block number:        11370156
   > block timestamp:     1663027399
   > account:             0x53aA0a0221a5Ea932Be1909E646d1f86491F2330
   > balance:             0.208102831489881768
   > gas used:            992479 (0xf24df)
   > gas price:           1.500000008 gwei
   > value sent:          0 ETH
   > total cost:          0.001488718507939832 ETH


   Deploying 'SolnSquareVerifier'
   ------------------------------
   > transaction hash:    0x5ca773ee382f366ebb72a25ded4aa6bf4943cc6ce4f3152f3718f48948bb5366
- Blocks: 0            Seconds: 0
- Blocks: 0            Seconds: 4
- Blocks: 0            Seconds: 8
- Blocks: 0            Seconds: 12
   > Blocks: 0            Seconds: 12
   > contract address:    0x8395ab676A41AebF8D47add9b2b6eaB16bD6D2cf
   > block number:        11370157
   > block timestamp:     1663027414
   > account:             0x53aA0a0221a5Ea932Be1909E646d1f86491F2330
   > balance:             0.203274604464131224
   > gas used:            3218818 (0x311d82)
   > gas price:           1.500000008 gwei
   > value sent:          0 ETH
   > total cost:          0.004828227025750544 ETH

- Saving migration to chain.
   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:     0.006316945533690376 ETH

Summary
=======
> Total deployments:   3
> Final cost:          0.006656751035502672 ETH

```  
### Contract Transaction Hash on rinkeby blockchain:  
- Verifier: 0xd4a63c553c5c938592e31672fca8c5d259003b0ea169e9b37a351dc91dbcff02 
- SolnSquareVerifier: 0x5ca773ee382f366ebb72a25ded4aa6bf4943cc6ce4f3152f3718f48948bb5366

### Contract Address on rinkeby blockchain:   
- Verifier: 0xD27F53208FBbeB58bE9f7143Adff02026800B66a  
- SolnSquareVerifier:  0x8395ab676A41AebF8D47add9b2b6eaB16bD6D2cf

### Deployed using MetaMask:
- Account: 0x53aA0a0221a5Ea932Be1909E646d1f86491F2330
https://rinkeby.etherscan.io/address/0x53aA0a0221a5Ea932Be1909E646d1f86491F2330

### Contract ABIs found in this GitHub repository:
- https://github.com/zeil156/Capstone-Real-Estate-Marketplace-Udacity-Project-Submission-/tree/main/Blockchain-Capstone/eth-contracts/build/contracts
- Use Verifier.json and SquareVerifier.json to view the ABIs

## OpenSea MarketPlace Storefront link
https://testnets.opensea.io/collection/custom-erc-token

# Project Resources
* [Remix - Solidity IDE](https://remix.ethereum.org/)
* [Visual Studio Code](https://code.visualstudio.com/) 
* [Truffle Framework](https://truffleframework.com/)
* [Ganache - One Click Blockchain](https://truffleframework.com/ganache)
* [Open Zeppelin ](https://openzeppelin.org/)
* [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)
* [Docker](https://docs.docker.com/install/)
* [ZoKrates](https://github.com/Zokrates/ZoKrates)
