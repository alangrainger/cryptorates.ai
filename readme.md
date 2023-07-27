## How to set up

There's nothing to install. Just copy and paste one of the formulas below and you're done!

To get the rate for a coin, use this formula:

```
=QUERY(IMPORTDATA("https://cryptorates.ai/files/standard.csv", ",", "en_US"), "SELECT Col3 WHERE Col1 = 'BTC'", 0)
```

You can replace the `BTC` with a cell reference (eg `"SELECT Col3 WHERE Col1='" & A1 & "'"`).

Alternatively you can import all rates at once, and use `VLOOKUP` or `INDEX` `MATCH` on your other sheets to look up the rates. Create a blank sheet and put this into A1:

```
=IMPORTDATA("https://cryptorates.ai/files/standard.csv", ",", "en_US")
```

## Changing currency - EUR, AUD, GBP, etc

Rates are in USD, so convert to any other currency using `GOOGLEFINANCE`, e.g.:

```
=QUERY(IMPORTDATA("https://cryptorates.ai/files/standard.csv", ",", "en_US"), "SELECT Col3 WHERE Col1 = 'BTC'", 0) * GOOGLEFINANCE("USDEUR")
```

## More info

For Excel go to Data > From Web, and paste this URL: https://cryptorates.ai/files/standard.csv

If you want more columns (volume, 24h change, etc), use `full.csv` instead of standard.

Data is updated every 30 minutes and includes the top 5000 coins by market cap

To output the time the data was fetched, use this formula:

```
=QUERY(IMPORTDATA("https://cryptorates.ai/files/standard.csv", ",", "en_US"), "SELECT Col2 WHERE Col1 = 'Updated at'", 0)
```

## Comments / questions?

For any issues or questions, please raise them here:

https://github.com/alangrainger/cryptorates.ai/issues
