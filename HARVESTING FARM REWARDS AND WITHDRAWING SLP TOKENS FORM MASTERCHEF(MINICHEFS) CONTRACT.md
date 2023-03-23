****************************************HARVESTING FARM REWARDS AND WITHDRAWING SLP TOKENS FORM MASTERCHEF/MINICHEF CONTRACT (UNSTAKING FROM A FARM)****************************************

- ****************************************************************Harvesting farm rewards from MasterchefV1****************************************************************  - on MasterchefV1 there is no “harvest” function, but users still can harvest their rewards buy calling “deposit” function, as this automatically harvest the rewards due to this moment.
1. Go to MasterchefV1 address on the block explorer and click "Contract"->“Write Conteract” ([https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract](https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract))
2. Connect your wallet (Connect to Web3)
    
    
3. Scroll to 2.deposit
4. In “_pid (uint256)” put the farm PID (pool ID)* - 31 

* The pool ID can be seen in the transaction for staking SLP. While on the page with transaction details click “+ Click to show more”

![Screenshot 2023-03-20 at 18.01.24.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2018.01.24.png)

After that click on “Decode Input Data”

![Screenshot 2023-03-20 at 18.02.05.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2018.02.05.png)

And you will see the pid of the given farm

![Screenshot 2023-03-20 at 18.02.43.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2018.02.43.png)

5. In the “_amount (uint256)” put 0
6. Click “Write”

![Screenshot 2023-03-20 at 18.08.13.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2018.08.13.png)

- **********************************************************************************************************************************Harvesting farm rewards from MasterchefV2 and Minichefs contracts**********************************************************************************************************************************
1. Go to the MasterchefV2 (Minichef) address on the block explorer and click "Contract"->“Write Conteract” ([https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract](https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract)) - Arbitrum example
2. Connect your wallet (Connect to Web3)
3. Scroll to 6.harvest
4. In “pid (uint256)” put the farm PID (pool ID)* - 12

* See above how to obtain PID number

5. In “to (address)” put user’s address - 0x54962fb1ba5229413777fbadd4d826319e68c065
6. Click “Write”

![Screenshot 2023-03-20 at 18.23.40.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2018.23.40.png)

- **Withdrawing SLP from MasterchefV1 (unstaking from a farm)**
1. Go to MasterchefV1 address on the block explorer and click "Contract"->“Read Conteract” ([https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#readContract](https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#readContract))
2. Scroll down to 14.userInfo
3. In “<input> (uint256)” put the pid number* - 12

* See above how to obtain PID number

4. In “<input> (address)” put the user address- 0x7887056691765941ada17fdeb59e41cbe18b340f
5. Click “query”
6. Copy “amount” value

![Screenshot 2023-03-20 at 18.48.14.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2018.48.14.png)

7. Click on “Write Contract” ([https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract](https://etherscan.io/address/0xc2EdaD668740f1aA35E4D8f227fB8E17dcA888Cd#writeContract))
8. Connect your wallet (Connect to Web3)
9. Scroll down to 12.withdraw
10. In “_pid (uint256)” put the farm pid - 12
11. In “_amount (uint256)” put the copied amount - 14134925891883420137
12. Click “Write”

The transaction will unstake user’s SLP and also will automatically harvest the user’s farm rewards.

![Screenshot 2023-03-20 at 19.01.47.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2019.01.47.png)

**********NOTE!********** There is also the “Emergency withdraw” function - 4.emergencyWithdraw, but if this function is called the user ******************will lose****************** the pending farm rewards! To call this function the user must enter just the pid number and click “write”. ****************************************************************************************************************************Should be used only if the user needs to unstake in emergency!****************************************************************************************************************************

- **Withdrawing SLP from MasterchefV2/Minichefs (unstaking from a farm)**

Unlike MasterchefV1, on MasterchefV2 and Minichefs users have the option to select “Withdraw and harvest” or just “Withdraw” (unstaking SLP without harvesting the farm rewards. Can be used if rewards contracts are out of the reward tokens, but the user wants to unstake anyway. Users can harvest their rewards later, when rewarder contracts are refilled). Inputs are absolutely the same for both functions - here is an Arbitrum example with calling “Withdraw” function.

NOTE! On MasterchefV2 the functions are under umbers 16 and 17 (16.withdraw, 17.withdrawAndHarvest) and on Minichefs these are under umbers 15 and 16 (15.withdraw, 16.withdrawAndHarvest)

1. Go to Minichefaddress on the block explorer and click "Contract"->“Read Conteract” ([https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#readContract](https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#readContract))
2. Scroll down to 12.userInfo (it is 14.userInfo for MasterchefV2)
3. In “<input> (uint256)” put the pid number* - 17

* See above how to obtain PID number

4. In “<input> (address)” put the user address- 0x54962fb1ba5229413777fbadd4d826319e68c065
5. Click “query”
6. Copy “amount” value

![Screenshot 2023-03-20 at 19.33.13.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2019.33.13.png)

7. Click on “Write Contract” ([https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract](https://arbiscan.io/address/0xf4d73326c13a4fc5fd7a064217e12780e9bd62c3#writeContract))
8. Connect your wallet (Connect to Web3)
9. Scroll down to 15.withdraw
10. In “_pid (uint256)” put the farm pid - 17
11. In “_amount (uint256)” put the copied amount - 110874089890529377
12. In “to (address)” put user’s address - 0x54962fb1ba5229413777fbadd4d826319e68c065
13. Click “Write”
![Screenshot 2023-03-20 at 19.37.43.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2019.37.34.png)
