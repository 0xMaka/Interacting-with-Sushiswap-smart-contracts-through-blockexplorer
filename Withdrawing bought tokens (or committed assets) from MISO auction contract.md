- **************************************Withdrawing bought tokens (or committed assets) from MISO auction contract**************************************

Before withdrawing tokens/committed assets from MISO auction first have to check that the auction is “finished” and - if it was successful - “finalised”. After the auction is finished (hit the end time), the owner of the auction have to finalise it if auction was successful. If the owner does not do that, 7 days after the end of the auction anyone can finalise the auction. So make sure that the auction is finished and finalised (if successful):

1. Go to the auction address on the block explorer - can find the address in the transaction with which assets were committed to the auction - and click “Contract”→”Read Contract”, for example: [https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#readContract](https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#readContract)
2. Scroll down to 5.auctionEnded - if it says “True” the action has ended, if it says “False” the auction is still running and the user should wait till it ends.
3. If auction is ended scroll down to 6.auctionSuccessful - if it says “True” the auction has reached the set targets and users will receive (when withdrawing) the tokens bought on the auction. If it says “false” the auction is not successful, does not need to be finalised and the users may proceed to withdraw the committed assets.
4. If the the auction was successful scroll down to 13.finalised - if it says “True”, the users may proceed with withdrawing the bought tokens. If it says “false” scroll up to 12.finalizeTimeExpired - if it says “false” the users have to wait till the owner of the auction finalise it or till the 7 days period expires. If it says “True” the users may finalise the auction themselves. To do that click on “Write Contract” ([https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract](https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract)), connect your wallet (Connect to Web3) scroll down to 11.finalize and click “Write”.

![Screenshot 2023-03-20 at 23.50.40.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2023.50.40.png)

- ************************************Withdrawing bought tokens/committed assets************************************

No matter if the users will withdraw tokens bought on the auction or committed assets, the procedure is the same:

1. Go to the auction address on the block explorer (can find the address in the transaction with which assets were committed to the auction) and click “Contract”→”Write Contract” ([https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract](https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract))
2. Connect your wallet (Connect to Web3)
3. Scroll down to 32.withdraw
4. Click “Write”

![Screenshot 2023-03-20 at 23.56.03.png](https://github.com/CarpeCryptum/pics/blob/main/Screenshot%202023-03-20%20at%2023.56.03.png)
