********************************************************************************REPAYING KASHI LOAN THROUGH THE CONTRACT********************************************************************************

To repay through the contract users should first deposit the asset they are going to repay to BentoBox, as calling repay function through the block explorer works only when using assets in user’s Bento balance. Can call “cook” function to repay from wallet, but the cook params are way more user unfriendly to generate. After depositing assets to Bento, the users have to obtain their borrowed part (amount of asset they have borrowed), so should go to the Kashi pair they have borrowed from (bsc chain example):

1. Go to the Kashi pair address on the block explorer and click "Contract"->“Read Contract” ([https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract](https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract))
2. Scroll down to 24.userBorrowPart
3. Put in the user address
4. Click “query”
5. Copy the userBorrowPart value

![Screenshot 2023-03-14 at 11.57.17.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-14%20at%2011.57.17.png)

6. Click on “Write Contract” ([https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract](https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract))
7. Scroll down to 13.reapy
8. In “to (address)” put user’s address
9. In “skim” put  false ( repaying with assets in user’s BentoBox balance)
10. In “part” put the copied amount
11. Click “write”

![Screenshot 2023-03-14 at 16.36.58.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-14%20at%2012.05.45.png)

Once the loan is repaid the users can withdraw their collateral. 

****************************************************************************WITHDRAWING COLLATERAL FROM KASHI PAIR****************************************************************************

1. Go to the Kashi pair address on the block explorer and click "Contract"->“Read Contract” ([https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract](https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract))
2. Scroll down to 25.userCollateralShare
3. Put in the user address
4. Click “query”
5. Copy the userCollateralShare value
6. Click on “Write Contract” ([https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract](https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract))
7. Scroll down to 12.removeCollateral
8. In “to (address)” put user’s address
9. In “share” put the copied amount
10. Click “write”

![Screenshot 2023-03-14 at 17.18.45.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-14%20at%2017.18.45.png)

The transaction will withdraw the collateral to the user’s Bento balance. After that the user can withdraw form there to the wallet (app.sushi.com→Portfolio→Account. The assets should be shown under “Bento” balance. Click on the asset and select “Withdraw to wallet).

************************************************************************************************WITHDRAWING DEPOSIT (LENT ASSET) FROM KASHI PAIR************************************************************************************************

1. Go to the Kashi pair address on the block explorer and click "Contract"->“Read Contract” ([https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract](https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract))
2. Scroll down to 5.balanceOf
3. Put in the user address
4. Click “query”
5. Copy the user balanceOf value

![Screenshot 2023-03-14 at 17.04.01.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-14%20at%2017.04.01.png)

6. Click on “Write Contract” ([https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract](https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract))
7. Scroll down to 11.removeAsset
8. In “to (address)” put user’s address
9. In “fraction” put the copied amount
10. Click “write”

![Screenshot 2023-03-14 at 17.15.16.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-14%20at%2017.15.16.png)

The transaction will withdraw the collateral to the user’s Bento balance. After that the user can withdraw from there to the wallet (app.sushi.com→Portfolio→Account. The assets should be shown under “Bento” balance. Click on the asset and select “Withdraw to wallet).
