# Gekko-datasets
Archives with datasets for the Gekko trading bot.

Extract the archives with tar or another decomperssing program.   
Put these datasets into your ~gekko/history/ folder and remove the part after the db extension.
e.g. 'binance_0.1.db_tot-1-2-2020' becomes 'binance_0.1.db'.

This archive contains the following datasets:
* binance_0.1.db-tot-1-2-2020 - dataset from 2019-02-01 00:00 to 2020-02-01 08:59
* binance_0.1.db_2017-09-01-2020-02-19 - dataset from 2017-09-01 to 2020-02-19


## Compressing, splitting and joining the databases
Larger files will not be uploaded to Github due to filesize restrictions (50Mb max). 
Therefore larger database files are zipped with bzip and splitted into files with a max size of 45Mb.
The procedure to zip, split, join and unzip these files is:

```
tar -cvjf binance_0.1.db-eth-2017-2020.tar.bz2 binance_0.1.db

split -b 45M binance_0.1.db-eth-2017-01-01_2020_02-20.tar.bz2 "binance_0.1.db-eth-2017-01-01_2020_02-20.tar.bz2.part"

ls -alh

cat binance_0.1.db-eth-2017-01-01_2020_02-20.tar.bz2.part* > binance_0.1.db-eth-2017-01-01_2020_02-20.tar.bz2

tar -xjfbinance_0.1.db-eth-2017-01-01_2020_02-20.tar.bz2
```
