# Harvesting farm rewards and withdrawing SLP tokens from Masterchef(Minichef) contracts

### Harvesting farm rewards from MasterchefV1

With MasterchefV1 there is no “harvest” function, but users can still harvest their rewards by calling "deposit". <br>
To do so we simply deposit 0 SLP token, passing the corresponding pool ID:

1. Go to MasterchefV1 address on the block explorer and click "Contract"->“Write Conteract” ([https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract](https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract))
2. Connect your wallet (Connect to Web3)    
3. Scroll to 2. deposit()
4. Under “\_pid (uint256)” input the farm's pool ID*
- \* The pool ID is a unique identifier, mapping the pool token to its allotment in the farm contract. <br>
  These can be found in the transaction for staking the SLP token.
- - While on the page with transaction details press “+ Click to show more”
![image](https://user-images.githubusercontent.com/12489182/228075061-8439657a-f7ee-4a55-a2df-b4e3b4466a63.png)
- - Then click on “Decode Input Data”
![image](https://user-images.githubusercontent.com/12489182/228075305-9b377a80-84df-4a92-a549-2d9c30a043e2.png)
- - This will reveal the pid of the given farm
![image](https://user-images.githubusercontent.com/12489182/228075189-9c35acfc-471f-4a50-80ff-34d55f75aef6.png)
5. Under the “\_amount (uint256)” field, input 0
6. Click “Write”
![image](https://user-images.githubusercontent.com/12489182/228086682-b67fba0b-0f99-4ad1-b4ad-336afc873eda.png)

### Harvesting farm rewards from MasterchefV2 and Minichefs contracts
1. Go to the MasterchefV2 (Minichef) address on the block explorer and click "Contract"->“Write Conteract” ([https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract](https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract)) - Arbitrum example
2. Connect your wallet (Connect to Web3)
3. Scroll to 6. harvest()
4. For “pid (uint256)”, input the farms unique identifier (pool ID) 
5. In the “to (address)” field, input the user’s address - *In this example: 0x54962fb1ba5229413777fbadd4d826319e68c065*
6. Click “Write”
![image](https://user-images.githubusercontent.com/12489182/228086556-83439555-dff6-4eff-9608-345d3fe2e584.png)

### **Withdrawing SLP from MasterchefV1 (unstaking from a farm)**

1. Go to MasterchefV1 address on the block explorer and click "Contract"->“Read Conteract” ([https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#readContract](https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#readContract))
2. Scroll down to 14. userInfo()
3. In “<input> (uint256)” put the pid number 
\* Here, it is 12, in another case it will be different. See above how to obtain PID number
4. In “<input> (address)” put the user address - *In this example 0x7887056691765941ada17fdeb59e41cbe18b340f*
5. Click “query”
6. Copy “amount” value <br> ![image](https://user-images.githubusercontent.com/12489182/228090954-1ee26234-1139-48fd-aa10-c4aabfe3126e.png)
7. Click on “Write Contract” ([https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract](https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract))
8. Connect your wallet (Connect to Web3)
9. Scroll down to 12. withdraw()
10. In “\_pid (uint256)” put the farm pid - *In this example: 12*
11. In “\_amount (uint256)” put the copied amount - *In this example: 14134925891883420137*
12. Click “Write”
- The transaction will unstake user’s SLP and also will automatically harvest the user’s farm rewards.
![image](https://user-images.githubusercontent.com/12489182/228090593-4ff4f012-b52d-4481-b279-3f8f4d55accf.png)

*NOTE!* There is also the “Emergency withdraw” function - 4.emergencyWithdraw, but if this function is called the user **will lose** the pending farm rewards! To call this function the user must enter just the pid number and click “write”. 
**Should be used only if the user needs to unstake in emergency!**

### Withdrawing SLP from MasterchefV2/Minichefs (unstaking from a farm)

Unlike MasterchefV1, for MasterchefV2 and Minichefs users have the option to select either “Withdraw and harvest”, or just “Withdraw” (unstaking SLP without harvesting the farm rewards. This can be useful if a reward contracts is out of the reward token, and the user still needs to unstake (*Note* this is not needed for v1 as reward is minted per block and cannot run out there). 
Where using wthdraw() without "harvest", users can harvest their rewards later, when rewarder contracts are refilled. 
Inputs are absolutely the same for both functions - Here is an Arbitrum example with calling “Withdraw” function.

*NOTE!* With MasterchefV2 the functions are under numbers 16 and 17 respoectively (16. withdraw(), 17. withdrawAndHarvest(), while for Minichefs, these are under numbers 15 and 16 (15. withdraw(), 16. withdrawAndHarvest())

1. Navigate to the Minichef address with a block explorer and click "Contract"->“Read Conteract” ([https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#readContract](https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#readContract))
2. Scroll down to 12. userInfo() (*Note* it is 14. userInfo() for MasterchefV2)
3. For the first field “<input> (uint256)”, enter the pid number - *In this example 17*
* Can see above how to obtain a farms PID
4. For the second “<input> (address)”, in put the user address - *In this eexample 0x54962fb1ba5229413777fbadd4d826319e68c065*
5. Click “query”
6. Copy “amount” value
![image](https://user-images.githubusercontent.com/12489182/228090974-565ec421-1f4e-4ae5-bae5-6c0976ca3bfd.png)
7. Click on “Write Contract” ([https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract](https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract))
8. Connect your wallet (Connect to Web3)
9. Scroll down to 15. withdraw()
10. For “\_pid (uint256)” input the farm pid - *Here 17*
11. Under “\_amount (uint256)” input the copied amount - *Here 110874089890529377*
12. In the “to (address)” field, input user’s address - *Here 0x54962fb1ba5229413777fbadd4d826319e68c065*
13. Click “Write”
![image](https://user-images.githubusercontent.com/12489182/228090840-82422e89-0a0c-4320-9f74-6c457d4c9675.png)
