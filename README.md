# binance-trade-bot

>Automated cryptocurrency trading bot

## Reasoning

The main theory behind this program is all cyrpto currencies having similar trends. As Bitcoin is the most known and highest valued coin, all currencies follow its lead.
A rise in price of Bitcoin triggers other crypto currencies in upwards trend.


## How?

The trading is done in the Binance market platform, which of course does not have markets for every altcoin pair. The workaround for this is to use Tether (USDT), which is stable by design, as a bridge currency.

<p align="center">
  Coin A → USDT → Coin B
</p>

The way the bot takes advantage of this behaviour is to always downgrade from the "strong" coin to the "weak" coin, under the assumption that at some point the tables will turn. It will then return to the original coin, ultimately holding more of it than it did originally. This is done while taking into consideration the trading fees.

<div align="center">
  <p><b>Coin A</b> → USDT → Coin B</p>
  <p>Coin B → USDT → Coin C</p>
  <p>...</p>
  <p>Coin C → USDT → <b>Coin A</b></p>
</div>

The bot jumps between a configured set of coins on the condition that it does not return to a coin unless it is profitable in respect to the amount held last. This means that we will never end up having less of a certain coin. The risk is that one of the coins may freefall relative to the others all of a sudden, attracting our reverse greedy algorithm.

## Binance Setup

* Create a [Binance account](https://www.binance.com/hw_register.html).
* Enable Two-factor Authentication.
* Create a new API key.
* Get a cryptocurrency. If its symbol is not in the default list, add it.

## Tool Setup

### Install Python dependencies

Run the following line in the terminal: `pip install -r requirments.txt`.

### Create user configuration

Create a .ini file named `user.cfg` based off `.user.cfg.example`, then add your API keys and current coin.

### Run

`./crypto_trading.py`

