# BSC Coin Sniper
This program allows you to instantly buy the given token after the liquidity transaction. You can snipe token launches and make profit.

# Which Network ?
This program is designed for `Binance Smart Chain`'s mainnet.

# How It Works ?
Coin Sniper filters out the pending transactions for the `PancakeSwap` and `DxSale` transactions and executes a `swapExactTokensForETH` call after the LP transaction.

# How Fast Is It ?
At the worst case scenario your swapping transaction would be in the next block of the LP transaction and It will take `3 seconds` to execute your call.
You could decrease that time with a private node to connect with WebSocket and also you can set extra gas to overrun the other transactions with `BUY_EXTRA_GWEI` in your configuration file. Second method is a bit risky because if you set a high value you could overrun the LP transaction and your gas money would go to trash but if you succeed your transaction can be in the same block as the LP transaction, so as summary it takes max. `3 seconds` to snipe.

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

```json
{
    "PRIVATE_KEY": "YOUR WALLET'S PRIVATE KEY",
    "WALLET_ADDRESS": "YOUR WALLET'S ADDRESS.",
    "PCS_ROUTER_ADDRESS" : "PANCAKESWAP ROUTER ADDRESS",
    "BSC_PROVIDER_ADDRESS": "YOUR BSC NODE'S WEBSOCKET ADDRESS",

    "COINS": [
        {   
            "IS_DXSALE_LAUNCH": false,
            "DXSALE_PRESALE_ADDRESS": "DXSALE PRESALE ADDRESS",
            "MIN_BNB_IN_LP_TX": 0.001,
            "TOKEN_ADDRESS": "TOKEN'S ADDRESS",

            "BUY_EXTRA_GWEI": 1,
            "BUY_AMOUNT": 0.001,
            "MAX_BUY_TRIES": 3,
            "STOP_IF_ALREADY_RELEASED": false,

            "SELL_AT": 2,
            "SELL_GAS_GWEI": 5,
            "SLIPPAGE_IN_PERCENT": 15,
            "AUTO_APPROVE": true
        }
    ]
}
```

# Config Object
* `PRIVATE_KEY`: Your wallet's private key. There is no way that any developer get that and no-one would ask too.
* `WALLET_ADDRESS`: Your wallet's address.
* `PCS_ROUTER_ADDRESS`: PancakeSwap router address. It's "0x10ED43C718714eb63d5aA57B78B54704E256024E" on BSC mainnet.
* `BSC_PROVIDER_ADDRESS`: BSC Node address. You can use the public WSS address if you want. (wss://bsc-ws-node.nariox.org:443)
* `COINS`: Your coin object list. You can add more coin object if you want.

# Coin Object
* `IS_DXSALE_LAUNCH`: If you are sniping an DxLaunch token make this `true` or if you don't make it `false`.
* `DXSALE_PRESALE_ADDRESS`: If you are not sniping an DxLaunch token leave it blank or put the presale address here.
* `MIN_BNB_IN_LP_TX`: Minimum BNB amount in liquidity transaction to snipe. It's a safety for not getting bogged by token's dev. traps.
* `TOKEN_ADDRESS`: Token's address.
* `BUY_EXTRA_GWEI`: Extra gas to append on `gasPrice` while buying. This could make the transaction executed faster or it could get you miss the launch. Keep it `0` or `1` if you trust yourself.
* `MAX_BUY_TRIES`: How many we will try if the buy transaction fails.
* `STOP_IF_ALREADY_RELEASED`: `true` if we don't want to snipe the next liquidity transaction or `false` if you want to snipe.
* `SELL_AT`: Sell multiplier. Program is going to sell the token when price reaches ex. 2x.
* `SLIPPAGE_IN_PERCENT`: Sell transaction slippage.
* `AUTO_APPROVE`: Approve the coin to the max. when selling.

# Contact
* DISCORD: `cool guy#4125`, `DEV#5502`
