# FreqtradeUtillityCommands
Overview of Freqtrade utillity commandfs


## Create commands

Create new user directory

```
freqtrade create-userdir --userdir /opt/freqtrade/user_data
```

Create new config

```
freqtrade new-config -c /opt/freqtrade/config.json
```

Create new strategy

```
freqtrade new-strategy --userdir /opt/freqtrade/user_data -s MyNewStrat --template [full/minimal/advanced]
```

## Inventory commands

List all the available strategies

```
freqtrade list-strategies --userdir /opt/freqtrade/user_data  --config config.json --strategy-path /opt/freqtrade/user_data/strategies/
```

List all the exchanges the bot (CCXT) supports

```
freqtrade list-exchanges --one-column
```

List the timeframes the given exchange supports

```
freqtrade list-timeframes --userdir /opt/freqtrade/  --config config.json --exchange binance
```

List pairs in a nice readable format

```
freqtrade list-pairs --exchange binance --all 
```

List all the available pairs, json format for the config file

```
freqtrade list-markets --userdir /opt/freqtrade/user_data/  --config config.json --exchange binance --print-json --quote USDT 

--base ETH
```

## Test commands

test your configuration of dynamic pairlists

```
freqtrade test-pairlist --config config.json --quote USDT 
```

## Show commands

Show the most recent backtesting results

```
freqtrade backtesting-show
```

Show all recent hyperopt results

```
freqtrade hyperopt-list
```

Show only best recent hyperopt results

```
freqtrade hyperopt-list --best
```

Show only most profitable recent hyperopt results

```
freqtrade hyperopt-list --profitable
```

Show hyperopt results from a hyperopt fila and export to csv

```
freqtrade hyperopt-list --profitable --hyperopt-filename=strategy_RsiStrat_2021-12-15_17-28-18.fthypt --export-csv MyHyperopt.csv
```

Show best recent hyperopt result without details

```
freqtrade hyperopt-list --best --no-details
```

Show hyperopt results from a hyperopt fila and export to csv

```
freqtrade show-trades --db-url sqlite:///user_data/tradesv3.sqlite --trade-ids 2 3 --print-json
```
