**********************************************WITHDRAWING ASSETS FROM BENTOBOX TO WALLET**********************************************

1. Go to the BentoBox address on the block explorer and click “Read Contract” ([https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#readContract](https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#readContract)) - Polygon chain example
2. Scroll down to 2.balanceOf
3. In the first field put the address of the token you want to withdraw - 0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39
4. In the second one put the user’s address - 0xD1134f6e28AB3b75500378b47250d6d88E0C1BB0
5. Click “query”
6. Copy the shown amount.

![image](https://user-images.githubusercontent.com/12489182/228032229-c975bff3-7ece-45fb-973d-eba4668d3fdf.png)

1. Click on “Write Contract” ([https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#writeContract](https://polygonscan.com/address/0x0319000133d3ada02600f0875d2cf03d442c3367#writeContract))
2. Connect your wallet (Connect to Web3)
3. Scroll down to 17.withdraw
4. In “token_(address)” put the token address - 0x53E0bca35eC356BD5ddDFebbD1Fc0fD03FaBad39
5. In “from (address)” put user’s address - 0xD1134f6e28AB3b75500378b47250d6d88E0C1BB0
6. In “to (address)” put user’s address - 0xD1134f6e28AB3b75500378b47250d6d88E0C1BB0 (yes, both “form” and “to” should be the user’s address)
7. In “amount (uint256)” put the copied amount - 574746746679140514
8. In “share (uint256)” put 0
9. Click “Write”

![image](https://user-images.githubusercontent.com/12489182/228032324-741e569a-0a55-4c9e-a3a9-e350bab22456.png)

