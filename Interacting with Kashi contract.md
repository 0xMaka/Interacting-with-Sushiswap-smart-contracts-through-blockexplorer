### REPAYING KASHI LOAN THROUGH THE CONTRACT

To repay through the contract users should first deposit the asset they are going to repay to BentoBox, as calling the repay function through the block explorer works only when using assets in user’s Bento balance. Can call “cook” function to repay from wallet, but the cook params are much less user unfriendly to generate. 
After depositing assets to Bento, the users have to obtain their borrowed part (amount of asset they have borrowed), so should go to the Kashi pair they have borrowed from (bsc chain example):

1. Go to the Kashi pair address on the block explorer and click "Contract"->“Read Contract” ([https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract](https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract))

2. Scroll down to 24. userBorrowPart()

3. Input in the user address

4. Click “query”

5. Copy the userBorrowPart value
![image](https://user-images.githubusercontent.com/12489182/228095261-ab76ec9f-cefb-4c0c-af60-38be5054ceda.png)

6. Click on “Write Contract” ([https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract](https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract))

7. Scroll down to 13. repay()

8. In “to (address)” put user’s address

9. In “skim” put  false (repaying with assets in user’s BentoBox balance)

10. In “part” put the copied amount

11. Click “write”
![image](https://user-images.githubusercontent.com/12489182/228095586-88bec8a2-3fb4-4822-8603-b9a1886a09d2.png)

Once the loan is repaid the users can withdraw their collateral. 

### WITHDRAWING COLLATERAL FROM KASHI PAIR

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
![image](https://user-images.githubusercontent.com/12489182/228096119-f3030069-1a5d-467a-b73f-ad4199512d12.png)

The transaction will withdraw the collateral to the user’s Bento balance. After that the user can withdraw form there to the wallet (app.sushi.com→Portfolio→Account. The assets should be shown under “Bento” balance. Click on the asset and select “Withdraw to wallet).

### WITHDRAWING DEPOSIT (LENT ASSET) FROM KASHI PAIR

1. Go to the Kashi pair address on the block explorer and click "Contract"->“Read Contract” ([https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract](https://bscscan.com/address/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#readContract))

2. Scroll down to 5. balanceOf()

3. Put in the user address

4. Click “query”

5. Copy the user balanceOf value
![image](https://user-images.githubusercontent.com/12489182/228096201-05a27e04-fc3b-4e95-8ce4-186c90c99fbb.png)

6. Click on “Write Contract” ([https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract](https://bscscan.com/token/0xAfa2526F518956a1FE1fF6f3Aef9A90007a64052#writeContract))

7. Scroll down to 11. removeAsset()

9. In “to (address)” put user’s address

10. In “fraction” put the copied amount

11. Click “write”
![image](https://user-images.githubusercontent.com/12489182/228096442-d9b987c1-29ff-430d-b17a-c8d30cf79672.png)

The transaction will withdraw the collateral to the user’s Bento balance. After that the user can withdraw from there to the wallet (app.sushi.com→Portfolio→Account. The assets should be shown under “Bento” balance. Click on the asset and select “Withdraw to wallet).
