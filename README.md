# Creating-a-Private-Blockchain
We host the private blockchain on Go-Ethereum(Geth)

1. Create a data directory 

mkdir blockchain 

2. initialize the genesis block

The genesis block is the first block in the blockchain 

geth --datadir blockchain init genesis.json

3. Start the Blockchain 

geth --identity "node01" --rpc --rpcaddr localhost --rpcport &quot;8000&quot; --rpccorsdomain &quot;*&quot;
--datadir blockchain1 --nodiscover --rpcapi
&quot;db,eth,net,web3,personal,miner,admin&quot; --networkid xxx --port 30303

--nodiscover Removes the possibility of Peer connection and only allows manual peer connection

--networkid Only nodes with the same networdid can connect to this chain 

4. Attach the geth console in another terminal 

geth attach ipc:\\.\pipe\geth.ipc

5. Start node 2

mkdir blockchain2

geth --identity "node02" --rpc --rpcaddr localhost --rpcport &quot;8000&quot; --rpccorsdomain &quot;*&quot;
--datadir blockchain2 --nodiscover --rpcapi
&quot;db,eth,net,web3,personal,miner,admin&quot; --networkid xxx --port 30304 console

6. Attach both nodes 

personal.newAccount() Creates a new account. A password creation will be prompted 

admin.nodeInfo This function is used to find enodeID

admin.addPeer() This function connects two nodes

admin.peers This function checks if the 2 nodes were paired

7. Using an external Wallet

You can use an external wallet such as MyEtherWallet or Mist to attach to your private blockchain to track transactions and balance

Or you can use the following functions 

eth.accounts Gives a list of all accounts on the blockchain

personal.unlockAccount() Unlocks Account

checkAllBalances() Displays all balances of each account

8. Start Mining 

miner.start() Starts the mining process 

miner.stop() Stops the mining process

9. Deploying Smart Contracts using truffle 

After installing truffle run 'truffle init'. This will load some files into your computer

Update the migrations folder with the name of your smart contract 

'truffle deploy' will deploy your contract


