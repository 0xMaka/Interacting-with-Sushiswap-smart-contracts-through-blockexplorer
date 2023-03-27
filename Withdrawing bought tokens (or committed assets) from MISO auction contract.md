### **************************************Withdrawing bought tokens (or committed assets) from MISO auction contract**************************************

Before withdrawing purchased tokens/committed assets from MISO auction, we first have to check that the auction is “finished” and - if it was successful - “finalised”. <br>
After the auction has finished (passed the end time), provided the auction was successful, the owner of the auction still has to finalise it. <br>
If the owner does not do that, then 7 days after the end time anyone can finalise the auction. 
So make sure that the auction is finished, and finalised (if successful):

1. Go to the auction address on the block explorer 
- - Can find the address in the transaction with which assets were committed to the auction - by clicking “Contract”→”Read Contract”. <br> 
    For example: [https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#readContract](https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#readContract)

2. Scroll down to 5. auctionEnded() 
- - “True” indicates the auction has ended, 
- - “False”, that the auction is still running and the users should wait till it ends.

3. If auction has ended, scroll down to 6. auctionSuccessful() 
- - “True” indicates the auction has reached the set targets, and users will receive (when withdrawing) the tokens bought at auction.
- - “False”, that the auction is not successful, does not need to be finalised and the users may proceed to withdraw the committed assets.

4. If the the auction was successful scroll down to 13. finalised() 
- If it says “True”, the users may proceed with withdrawing the bought tokens. If it says “False” scroll up to 12.finalizeTimeExpired() - if this shows “false” the user will have to wait, either for the auction owner to finalise it, or for the 7 day period to expire. <br>
If it says “True” the users may finalise the auction themselves. 
To finalise an auction click on “Write Contract” ([https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract](https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract)) <br>
Connect your wallet (Connect to Web3) scroll down to 11.finalize and click “Write”.

![image](https://user-images.githubusercontent.com/12489182/228038394-27b3ff0a-e0ab-499c-bbc4-c4c4f26ec090.png)

### ************************************Withdrawing bought tokens/committed assets************************************

No matter if the users will withdraw tokens bought on the auction or committed assets, the procedure is the same:

1. Go to the auction address on the block explorer (can find the address in the transaction with which assets were committed to the auction) and click “Contract”→”Write Contract” ([https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract](https://etherscan.io/address/0x6629F31a192cDfc3A21FBd7753885946039AD43D#writeContract))
2. Connect your wallet (Connect to Web3)
3. Scroll down to 32.withdraw
4. Click “Write”

![image](https://user-images.githubusercontent.com/12489182/228038571-c53914f8-4123-450b-8d59-7bc505ac67ea.png)
