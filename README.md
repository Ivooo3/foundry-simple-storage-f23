# Learned with this contract :
- Create foundry project with ```forge --init```
- Start foundry with ```anvil``` command ()
- Create ```DeploySimpleStorage.s.sol``` script to deploy ```SimpleStorage.sol``` contract
- Create ```.env``` file to contains key/value variables (do not put real ```Private key``` in there!)
  - use ```source .env``` command to load the variables
- Deploy script to localhost 
    ```
    forge script script/DeploySimpleStorage.s.sol --rpc-url $RPC_URL --private-key $PRIVATE_KEY
    ```
  - deploy on Sepolia test network using ```alchemy``` with ```forge``` command 
    ```
    forge script script/DeploySimpleStorage.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast
    ```
- Test ```set``` function with given param on the deployed contract using ```cast send``` command
    - we take ```0x5FbDB2315678afecb367f032d93F642f64180aa3``` after we deploy the contract
    ```
    cast send 0x5FbDB2315678afecb367f032d93F642f64180aa3 "store(uint256)" 777 --rpc-url $RPC_URL --private-key $PRIVATE_KEY
    ```
- Test ```get``` function on the deployed contract with ```cast call ``` command
    ```
    cast call 0x5FbDB2315678afecb367f032d93F642f64180aa3 "retrieve()"
    ```
- we can use ```cast --to-base ``` to test if the correct value is saved in our set function
    ```
    cast --to-base 0x0000000000000000000000000000000000000000000000000000000000000309 dec 
    ```
- ```anvil``` - deploy local blockchain
- ```forge``` - compiling and interactive with contracts
- ```cast``` - interacting with contracts already deployed