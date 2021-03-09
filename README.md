# blockchain-homework

# How to Start the Network 

Installation: 

1.For the block chain to work there are a few sofrwares we will need: 
 geth - https://geth.ethereum.org/downloads/
 mycrypto wallet - https://download.mycrypto.com/

2. Once you download the geth application unzip the contents into a folder.
3. Then open "GitBash" use the cd function to change the present working directory into the folder you just created
4. Now type in as follows: /geth --datadir node1 account new this will create a new node for us to work with 
5. Once the node is created you will see that it gives a public key and secret key SAVE THESE as we need them to access the nodes![nodesetup](https://user-images.githubusercontent.com/69990029/110523222-ce2c3c80-80df-11eb-959b-f143be8bf21e.png)

6. Do the same once more to create a second node make sure to name is somehting else: ./geth --datadir node2 account new
7. Now that the nodes are created we need to launch "Puppeth" to create our network:
- in gitbash type ./puppeth 
- choose a network name
- select "configure new genesis"
- select "create new genesis from scratch"
- select Clique 
- when asked How many seconds should block take click enter to stick with default 
- now it will ask which account are allowed to seal this is where you enter in both of the public addresses of the nodes EXCLIUDING the 0x at the start of the address hit enter twice to move to the next step 
- when asked should precomplie be pre-funded type in: no
- then when asked to create a chain ID: use just a few numbers to keep it simple such as 555
- then select manage cexisting genesis
- Export genesis
- then it will ask which folder to save to just hit enter as we want it to save where the nodes are 
- the network is now setup click control + c to exit out of the setup

![networksetup](https://user-images.githubusercontent.com/69990029/110524162-0a13d180-80e1-11eb-954f-2166be80e46a.png)
![networksetup2](https://user-images.githubusercontent.com/69990029/110524167-0c762b80-80e1-11eb-958c-9f4b44f0cc1b.png)


8. Now we must initialze the nodes to do this we type in Gitbash:
  - ./geth --datadir node1 init "NETWORKNAME".json **replace NETWORKNAME with the netwrok name you chose 
  - do the same now for node 2 ./geth --datadir node2 init {networkname}.json
9. Now open up a new GitBash window and type in ./geth --datadir node1 --unlock "*****NODE 1 PUBLIC KEY" --mine --minerthreads 1 **** replace with node1 public key 
10. As soon as you run this code you will see a lot of processing you need to extract the enode address to do this look through the processign and you will see a line that starts with self:enode copy the whole line
![enode](https://user-images.githubusercontent.com/69990029/110525532-ae4a4800-80e2-11eb-8dd6-bbcd57c0ef3e.png)

12. Now once again open another GitBash window and type in  ./geth --datadir node2 --unlock "**NODE 2 PUBLIC ADDRESS" --port 30304 --rpc --bootnodes "***ENODE ADDRESS " --ipcdisable --allow-insecure-unlock
** Put the node 2 public key there
***Put the enode address including the word enode

13. The Blockchain is now running
14. Open the Mycrypto app 
15. click on Keystore File
16. ![KeystoreFile](https://user-images.githubusercontent.com/69990029/110526901-5b719000-80e4-11eb-8a99-0366f4cafc19.png)

17. you must now enter the file located in your node file *you can enter either one
18. Then enter the password you created 
19. ![login](https://user-images.githubusercontent.com/69990029/110527017-7ba14f00-80e4-11eb-9376-d2599ff0a673.png)

20. Now you are in the node
21. now we need to connect to our network **Make sure the nodes are running 
22. on the left side click Change network 
23. ![network](https://user-images.githubusercontent.com/69990029/110527127-95429680-80e4-11eb-96cd-c21f50ebb647.png)

24. scroll all the way down to + Add custom Node 
25. now to set up the network all you  have to do is:
  - enter a node name then 
  - on the network scroll down meue select custom 
  - enter the network name you assigned at the start
  - write ETH for the currency to use ethereum
  - enter the chain/network ID you assigned
  - for the URL you will see a greyed out url re-write that as it is a generic 
  - click the blue Save& Use Custom Nude button 
  - ![networksretup](https://user-images.githubusercontent.com/69990029/110527414-ed799880-80e4-11eb-8090-36d534cc7925.png)


23. now that you are connected go ahead and send your self some ether
24. type in the public key of the node you are not currentlty in 
25. type in an amount and send 
26. you will get a notice at the bottom saying the amount has sent and to view the transaction
27. If you go back on to your GitBash you will see on one of your the nodes "transaction sumbitted" this is how you can see and verify for youself that it went
![transsubmitted](https://user-images.githubusercontent.com/69990029/110527590-27e33580-80e5-11eb-9542-a1d04cf6515e.png)

29. Going back to the crypto wallet click on the view status on the bottom message and it will log you out and take you to a different page where you can see the status and details at first it will say pending give it a few moments and it will change to sucessful. 

![submitted](https://user-images.githubusercontent.com/69990029/110527672-40ebe680-80e5-11eb-8413-565649abb0e1.png)






