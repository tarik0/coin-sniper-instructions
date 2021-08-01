# BSC Coin Sniper
This program allows you to instantly buy the given token after the liquidity transaction. You can snipe token launches and make profit.

# Which Network ?
This program is designed for `Binance Smart Chain`'s mainnet.

# How It Works ?
Coin Sniper filters out the pending transactions for the `PancakeSwap` and `DxSale` transactions and executes a `swapExactTokensForETH` call after the LP transaction.

# How Fast Is It ?
You can snipe the token in the first block with private nodes like `getblock.io`.

# Supported Transaction Types
Not all transactions in all platforms are supported. Those are the supported platforms and transaction types.

1. DxSale Finalization Transactions.
2. PancakeSwap Liquidity Adding Transactions.

# Quick Tools Menu
At the `Tools` section of the top menu, you can open shortcut websites like `DxSale`, `PancakeSwap` and `Bscscan.`

# Bug Reporting.
Bug reporting is a critical thing for us. If you are facing with an error or if the program does not works like it should be please contact with an developer and send your debug logs and screenshots of the program.

You can generate your debug logs using `Tools->Save Debug Logs` and you can reload your application using `Tools->Reload Application`.
(The debug log's won't include your wallet's private key.)

# How To Write A Config File
The configuration file is actually a JSON file.

```yml
# Your wallet settings.
Wallet Settings:
  Private Key: ""
  Wallet Address: ""

# Your PancakeSwap and node settings.
Network Settings:
  PancakeSwap Address: ""
  Websocket Provider: ""

# The list of target coins that you want to snipe.
Target Coins:
  - Token Address: ""  # Enter the address of the token that you wan't to snipe here.

    # DxSale settings.
    Is DxSale Launch: false  # If you are sniping an DxSale launch make that `true`.
    DxSale Presale Address: ""  # If you are sniping an DxSale launch, enter the presale address here.

    # Anti-bot settings.
    Min. Liquidity Amount in BNB: 0.1  # The minimum liquidity amount to detect.
    Buy Delay in Sec: 0  # The buy execution delay after detecting liquidity. (3 seconds =~ 1 block)
    
    # Other settings.
    Stop If Tokens Are Already Released: false  # On `true` stops sniping if the tokens are already released.

    # Approving settings.
    Auto Approve: true  # On `true`, approves the token to the max. before sniping.
    Approve Gas Price in GWEI: auto  # You can set your approve transaction's gas price here. (Auto is recommended.)
    Approve Gas Limit: auto  # You can set the approve transaction's gas limit manually here. (Auto is recommended.)

    # Buy settings.
    Buy Amount in BNB: 0.1  # The amount of BNBs that you wan't to swap.
    Max. Buy Retries: 3  # Amount of retries if buying it's fails. 
    Buy Gas Price in GWEI: auto  # You can set the buy transaction's gas price manually here. (Auto is recommended.)
    Buy Gas Limit: auto  # You can set the buy transaction's gas limit manually here. (Auto is recommended.)

    # Sell settings.
    Auto Sell: true  # On `true` after the token is sniped bot sells the tokens at a target price.
    Sell Slippage: 15  # Slippage in percentage.
    Sell At Multiplier: 5  # Target price multiplier to sell tokens at. (ex. this sells at 5X.)
    Sell Gas Price in GWEI: auto  # You can set the sell transaction's gas price manually here. (Auto is recommended.)
    Sell Gas Limit: auto  # You can set the sell transaction's gas limit manually here. (Auto is recommended.)
```

# Contact
* DISCORD: `cool guy#4125`, `DEV#5502`
