> **_NOTE_**<br>
> PLEASE KEEP IN MIND THAT ALL VALUES (AMOUNTS, ADDRESSES, ETC..) ARE JUST FOR EXAMPLE. WHEN INTERACTING WITH THE SMART CONTRACTS USERS SHOULD USE THEIR OWN WALLET ADDRESSES, CORRESPONDING CONTRACT ADDRESSES AND AMOUNT VALUES !!!
1. Go to NonfungiblePositionManager contract address on the block explorer (for the desired chain - here we use an Arbitrum example) and select "Read contract"/"Read as proxy"
([https://arbiscan.io/address/0xF0cBce1942A68BEB3d1b73F0dd86C8DCc363eF49#readProxyContract](https://arbiscan.io/address/0xF0cBce1942A68BEB3d1b73F0dd86C8DCc363eF49#readProxyContract))
2. Scroll down to 11.positions, click on it and enter the ID of the NFT token that represent your liquidity postion. Then click "query"
3. Copy the liquidity amount ![image](https://github.com/CarpeCryptum/pics/blob/bb87fb890ed366f0bd74b4ccb8b8f8af0a6c7c46/Screenshot%202023-09-16%20at%2015.57.00.png)

4. Select "Write contract"/Write as proxy"
5. Connect to web3
6. Scroll down to 5.decreaseLiquidity and click on it
7. In the first field (decreaseLiquidity) put 0, in the second put the params, which are as follow: your token ID, your liquidty amount (the one you coppied from "Read Contract"), the minimum amopunt of the first token (token0) you would accept, the mininimum amount of second token (token1) you would accept, deadline(the date - in unixtimestamp - after which the transaction should fail if have not been processed yet). Keep in mnind that token amounts should be in unit 256, so check the decimals of each token
![image](https://github.com/CarpeCryptum/pics/blob/f2334cbb80fbbfd28a5eaa4b5e5d00ee5912c83b/Screenshot%202023-09-16%20at%2017.41.52.png)
8. Click "write". If the transaction cost shown on user's wallet is too high it means there is a problem, so should not be confiremed. Have to check all the data and if there are no errors may simulate the transaction on Tennderly to see what the problem may be.
9. After successfull decreaseLiquidity transaction go to 3.collect. In the first field (collect) put 0. In the second field put the following params: your token ID, **YOUR ADDRESS**, max amount of token0 you want to receive, max amount of token1 you want to receieve (max amounts can be any nuber greater than the number of tokens your postions holds). Keep in mind that "decreaseLiquidity" function increases your "unclaimed" fees with the amounts with which the liquidity was decreased. So when calling "collect" (which collects unclaimed fees) you should take into account the amount of those fees when setting the AmountMAX values for token0 and token1.
![image](https://github.com/CarpeCryptum/pics/blob/ad8e46dfd009bc335458fc3cba30f9574629b29b/Screenshot%202023-09-16%20at%2018.00.36.png)
10. Click "write". If the transaction cost shown on user's wallet is too high it means there is a problem, so should not be confiremed. Have to check all the data and if there are no errors may simulate the transaction on Tennderly to see what the problem may be.
