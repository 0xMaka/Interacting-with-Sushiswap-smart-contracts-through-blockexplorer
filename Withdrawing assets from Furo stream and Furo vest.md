# ********************WITHDRAWING ASSETS FROM FURO STREAM AND FURO VEST********************

### **************************************Withdrawing from FURO STREAM**************************************

1. Go to the FURO STREAM contract address on the block explorer and click “Contract”→”Read Contract” ([https://polygonscan.com/token/0x4ab2fc6e258a0ca7175d05ff10c5cf798a672cae#readContract](https://polygonscan.com/token/0x4ab2fc6e258a0ca7175d05ff10c5cf798a672cae#readContract)) Polygon example
2. Scroll down to 10. streamBalanceOf()
3. In “streamId (uint256)” put the stream ID* - 1041
4. Click “query”
5. Copy the recipientBalance amount

![image](https://user-images.githubusercontent.com/12489182/228024146-37a204ac-5baf-4aff-9fec-1f6531e2dd8e.png)

6. Click on “Write Contract”
7. Connect your wallet (Connect to Web3)
8. Scroll down to 15. withdrawFromStream()
9. In “streamId (uint256)” put the stream ID - 1041
10. In “sharesToWithdraw (uint256)” put the copied amount - 981971910784803885
11. In “withdrawTo (address)” put the user’s address - 0x4E3FEcA86CfdF57BE3e64435aa1FE6E18C498500
12. In “toBentoBox (bool)” put - false (to withdraw assets to wallet) or true (to withdraw assets to user’s BentoBox balance)
13. In “taskData (bytes)” put - 0x
14. Click “Write”

![image](https://user-images.githubusercontent.com/12489182/228024711-7b09a0f4-87c9-445a-b145-404465f2b364.png)

* Can find the stream ID in the transaction for receiving the FURO STREAM token - Check user’s address, under ERC-721 Token Txns

![image](https://user-images.githubusercontent.com/12489182/228024775-6f40e25f-12f3-48ec-84cb-827f1f78b951.png)

###  **********************************************WITHDRAW FROM FURO VEST**********************************************
1. Go to FURO VEST contract address on the block explorer and click “Contract”→”Read Contract” ([https://arbiscan.io/address/0x0689640d190b10765f09310fcfe9c670ede4e25b#writeContract](https://arbiscan.io/address/0x0689640d190b10765f09310fcfe9c670ede4e25b#writeContract)) Arbitrum example
2. Connect your wallet (Connect to Web3)
3. Scroll down to 14. withdraw()
4. In “vestId (uint256)” put the vest ID (see above how to obtain the ID - same as for stream ID) - 3
5. In “taskData (bytes)” put - 0x
6. In “toBentoBox (bool)” put - false (to withdraw assets to wallet) or true (to withdraw assets to user’s BentoBox balance)
7. Click “Write”

![image](https://user-images.githubusercontent.com/12489182/228024922-e8d926d4-6fe4-4531-9518-9883f269818e.png)
