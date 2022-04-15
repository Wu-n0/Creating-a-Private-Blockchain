# Creating-a-Private-Blockchain
We host the private blockchain on Go-Ethereum(Geth)

1. Create a data directory 

mkdir blockchain 

2. initialize the genesis block

The genesis block is the first block in the blockchain 

geth --datadir blockchain init genesis.json

3. Start the Blockchain 

geth --rpc --rpcaddr localhost --rpcport &quot;8000&quot; --rpccorsdomain &quot;*&quot;
--datadir blockchain --nodiscover --rpcapi
&quot;db,eth,net,web3,personal,miner,admin&quot; --networkid xxx

--nodiscover Removes the possibility of Peer connection and only allows manual peer connection

--networkid Only nodes with the same networdid can connect to this chain 

4. 
