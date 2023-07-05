# Creating-a-Private-Blockchain

This project focuses on creating a private blockchain using Go-Ethereum (Geth).

## Setup Instructions

1. Create a data directory for the blockchain:

mkdir blockchain

2. Initialize the genesis block:

The genesis block is the first block in the blockchain.

geth --datadir blockchain init genesis.json

3. Start the Blockchain:

geth --identity "node01" --rpc --rpcaddr localhost --rpcport "8000" --rpccorsdomain "*" \
--datadir blockchain1 --nodiscover --rpcapi "db,eth,net,web3,personal,miner,admin" \
--networkid xxx --port 30303

- The `--nodiscover` flag removes the possibility of peer connection and only allows manual peer connection.
- The `--networkid` flag ensures that only nodes with the same network ID can connect to this chain.

4. Attach the Geth console in another terminal:

geth attach ipc:\\.\pipe\geth.ipc

5. Start node 2:

mkdir blockchain2

geth --identity "node02" --rpc --rpcaddr localhost --rpcport "8000" --rpccorsdomain "*" \
--datadir blockchain2 --nodiscover --rpcapi "db,eth,net,web3,personal,miner,admin" \
--networkid xxx --port 30304 console

6. Attach both nodes:

- Create a new account: `personal.newAccount()` (A password creation prompt will appear)
- Find enodeID: `admin.nodeInfo`
- Connect two nodes: `admin.addPeer()`
- Check if the nodes are paired: `admin.peers`

7. Using an external wallet:

You can use an external wallet such as MyEtherWallet or Mist to attach to your private blockchain and track transactions and balances. Alternatively, you can use the following functions:

- Get a list of all accounts on the blockchain: `eth.accounts`
- Unlock an account: `personal.unlockAccount()`
- Display all balances of each account: `checkAllBalances()`

8. Start mining:

- Start the mining process: `miner.start()`
- Stop the mining process: `miner.stop()`

9. Deploying Smart Contracts using Truffle:

- After installing Truffle, run `truffle init` to load some files into your computer.
- Update the migrations folder with the name of your smart contract.

Feel free to explore the source code, modify it to fit your specific requirements, and contribute to the project by submitting pull requests or opening issues.

## Contributing

Contributions to this project are welcome. If you encounter any issues, have suggestions for improvements, or want to contribute new features, please feel free to submit a pull request or open an issue.



