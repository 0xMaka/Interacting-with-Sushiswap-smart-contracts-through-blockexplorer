**********************************************WITHDRAWING ASSETS FROM BENTOBOX TO WALLET**********************************************

1. Go to the BentoBox address on the block explorer and click “Read Contract” ([https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#readContract](https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#readContract)) - Polygon chain example
2. Scroll down to 2.balanceOf
3. In the first field put the address of the token you want to withdraw - 0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39
4. In the second one put the user’s address - 0xD1134f6e28AB3b75500378b47250d6d88E0C1BB0
5. Click “query”
6. Copy the shown amount.

![Screenshot 2023-03-19 at 18.31.58.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-19%20at%2018.31.58.png)

1. Click on “Write Contract” ([https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#writeContract](https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#writeContract))
2. Connect your wallet (Connect to Web3)
3. Scroll down to 17.withdraw
4. In “token_(address)” put the token address - 0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39
5. In “from (address)” put user’s address - 0xD1134f6e28AB3b75500378b47250d6d88E0C1BB0
6. In “to (address)” put user’s address - 0xD1134f6e28AB3b75500378b47250d6d88E0C1BB0 (yes, both “form” and “to” should be the user’s address)
7. In “amount (uint256)” put the copied amount - 574746746679140514
8. In “share (uint256)” put 0
9. Click “Write”

![Screenshot 2023-03-19 at 18.31.58.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-19%20at%2018.45.19.png)
