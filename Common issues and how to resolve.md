# Most common issues

### **I made a swap but did not receive the token I swapped into** 
- Most likely you just submitted an approval transaction and still need to make the actual swap. You can always check the type and status of your transactions via the chain block explorer. If you want to know more about “approval”, please see here: [https://www.sushi.com/academy/articles/what-is-token-approval](https://www.sushi.com/academy/articles/what-is-token-approval)

### **I don’t see the token I bought in my Metamask** 
- In most cases you must add the token to your MM. Please check the manual:  [https://www.sushi.com/academy/articles/add-unlisted-token-on-metamask](https://www.sushi.com/academy/articles/add-unlisted-token-on-metamask)

### **Farms, pools or “my position” not showing on the UI** 
- Most likely needs to clear browser cookies and cache and hard refresh the site after that. In some cases it may be caused by a slow RPC. You can check the quality of RPCs here: [https://chainlist.org/](https://chainlist.org/). And here is a manual how to change the RPC in your Metamask: [https://support.samurais.io/article/how-to-change-rpc-on-metamask](https://support.samurais.io/article/how-to-change-rpc-on-metamask) . Specifically for pool (LP) position, if going through the old UI (app.sushi.com), make sure that the SLP tokens are in your wallet (not staked in a farm or other protocol), if still not seeing your position you may need to import it - [https://support.samurais.io/article/importing-a-pair-that-does-not-appear-on-sushis-interface](https://support.samurais.io/article/importing-a-pair-that-does-not-appear-on-sushis-interface)

### **“Confirm” (swap, deposit, withdraw, order) button do not trigger MM** 
- probably a RPC problem (please see above how to resolve it). Another common reason is having two wallets active at the same time (usually MM plus Brave wallet or Trust wallet, etc..). Please check and close all wallets not being used at the moment. Slippage settings can also cause problems for swap and withdraw transactions, especially when interacting with low liquidity pools or pools where one of the assets price is near 0. As new UI (sushi.com/swap) does not support selling tokens with tax (and does not allow setting slippage when removing liquidity), you have to use the old UI - [app.sushi.com](http://app.sushi.com) for that type of tokens and set the slippage in accordance with the token tax. Another problem may be that in a token “ABC”/ETH pool, token “ABC” may have some broken liquidity tax mechanics in its code, so you may need to select to receive WETH instead of ETH (the option is possible on app.sushi.com), when trying to remove liquidity. If non of the above helps, please make a screenshot of the console errors (right click somewhere on the webpage, select inspect→console→errors) and create a support ticket in #support-ticket channel on Discord

### **I can not unstake from a farm or harvest my farm rewards** 
- For the side chains: the minichef is out of sushi. Should wait for a refill (usually takes couple of days) or can use [sushibackup.com/farm](http://sushibackup.com/farm) to unstake without harvesting. Your 2nd token rewards will be automatically harvested (though you selected just “unstake”) and you will be able to harvest your SUSHI rewaerds later, when the minichef contract is refilled, just keep in mind that you will have to stake again some small amount of SLP to be bale to harvest.

### **I unstaked/harvested but only got the sushi rewards and not the “2nd” token rewards** 
- the rewarder holding “2nd” token rewards is drained out and need to be refilled. Usually the “2nd” token rewards are managed by the protocols the token belongs to and it is entirely up to them to refill.

### **********My transactions for claiming rewards/removing liquidity, etc are failing********** 
- most likely gas amount limit or gas price are too low. Check on the block explorer if a failed transaction has used all the possible amount of gas. If so try again, but increase the gas amount limit in your wallet before confirming the transaction.

### **I placed a limit order, but do not see it in my open orders list** 
- Most likely just deposited your funds to your BentoBox balance and did not complete setting the order. Please check your BentoBox balance at app.sushi.com→Portfolio→Account. If your funds are there you may complete the order by starting the process from the beginning, just this time select “BentoBox” when setting the “Pay from” option.

### **I made a cross-chain swap but did not receive the tokens on the destination chain** 
- In some rare cases you may receive the assets in the form of stable coins on the destination chain. This may happen if the swap ratio (stables to “desired asset”) is not good enough to meet the minimum amount you have set on the initiating chain. So to protect you against unfavourable trade the assets will be left in stables. Can check the status of your cross-chain transaction here: [https://layerzeroscan.com/](https://layerzeroscan.com/)

### **I am trying to make a cross-chain swap, but I am getting the “insufficient balance” message** 
- The message is about the amount of the native token you have on the initiating chain. As all transaction fees (even the ones due on the destination chain) are paid on the initiating chain, make sure that you have enough of the chain native token to pay the fees.

### **I provided collateral and borrowed on a KASHI pair, but did not get the borrowed asset in my wallet** 
- Most likely used the “leverage” option, which automatically swaps the borrowed asset into the collateral one and thus increases the amount of your collateral. Please check your collateral balance. To repay your debt you should use “close position” option (do not enter values under “Repay” and “Remove”), which will sell your collateral (in amount needed to cover the debt) for the borrowed asset and repay. You can also market buy the borrowed asset and use it to repay the debt from your wallet/bento balance and withdraw all your collateral.
