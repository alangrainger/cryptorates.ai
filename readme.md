## How to set up

There's nothing to install. Just copy and paste one of the formulas below and you're done!

To get the rate for a coin, use this formula:

```
=QUERY(IMPORTDATA("https://cryptorates.ai/files/standard.csv", ",", "en_US"), "SELECT Col3 WHERE Col1 = 'BTC'", 0)
```

You can replace the "BTC" with a cell reference (eg `"SELECT Col3 WHERE Col1='" & A1 & "'"`).

Alternatively you can import all rates at once, and use `VLOOKUP` or `INDEX` `MATCH` on your other sheets to look up the rates. Create a blank sheet and put this into A1:

```
=IMPORTDATA("https://cryptorates.ai/files/standard.csv", ",", "en_US")
```

## Changing currency - EUR, AUD, GBP, etc

Rates are in USD, so convert to any other currency using `GOOGLEFINANCE`. See the demo sheet for an example of how to do this.

## Live demo

Have a look at this demo portfolio example, or take a copy and make it your own:

[Open the demo spreadsheet](https://docs.google.com/spreadsheets/d/1nu7EYtzxrizrypDvnrtz5FrfTBDpFLkjk7Lw80blUEc/edit?usp=sharing)

## More info

For Excel go to Data > From Web, and paste this URL: https://cryptorates.ai/files/standard.csv

If you want more columns (volume, 24h change, etc), use `full.csv` instead of standard.

Data is updated every 30 minutes. For the standard dataset, it's the top 4000 coins by market cap. For the full dataset, it's the top 2000 coins to keep the import filesize small.

## Comments / questions?

For any issues or questions, please raise them here:

https://github.com/alangrainger/cryptorates.ai/issues
