# Gekko-datasets
Archives with datasets for the Gekko trading bot.
Dataset contains BTC and ETH data.

Extract the archives with tar or another decomperssing program.   
Put these datasets into your ~gekko/history/ folder and remove the part after the db extension.

## Compressing, splitting and joining the databases
Larger files will not be uploaded to Github due to filesize restrictions (50Mb max). 
Therefore larger database files are zipped with bzip and splitted into files with a max size of 45Mb.
The procedure to zip, split, join and unzip these files is:


### Compressing and cutting the database
```
tar -cvjf binance_0.1.2017-2021.tar.bz2 binance_0.1.db

split -b 45M binance_0.1.2017-2021.tar.bz2 "binance_0.1.2017-2021.tar.bz2.part"

rm binance_0.1.2017-2021.tar.bz2


ls -alh
```

### Joining the split files

```
cat binance_0.1.2017_2021.tar.bz2.part* > binance_0.1.2017_2021.tar.bz2

tar -xjf binance_0.1.2017_2021.tar.bz2
```
