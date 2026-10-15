# waistline-bls
Bundeslebensmittelschlüssel (BLS) German food database converted to Waistline import format

# BLS database for Waistline

German food composition database from Max Rubner Institut converted
to the import JSON format used by Waistline.

## About Waistline

Waistline is a libre calorie counter and weight tracker app for Android. It's built with Cordova, Framework7, and a few other free libraries.

https://github.com/davidhealey/waistline

## About Max Rubner Institut and the BLS database

The Max Rubner Institut (MRI) is a higher federal authority of the Federal Republic of Germany in the portfolio of the Federal Ministry of Food and Agriculture (BMEL). The research focus is on consumer health protection in the nutrition sector.

MRI maintains the Bundeslebensmittelschlüssel (BLS, translates to Federal Food Key) database, a reference database providing the nutritional composition of foods commonly consumed in Germany.

The BLS database contains nutritional information such as:
- energy values,
- proteins,
- carbohydrates,
- fats,
- fibres,
- vitamins,
- minerals,
- and other nutrients.

It holds more than 7000 food entries.

This project converts the official BLS database into the JSON format required by the Waistline application.

Food names are in German and English language.

## Source

Original data:

Max Rubner-Institut (2025): Bundeslebensmittelschlüssel (BLS), Version 4.0. Karlsruhe.

https://www.blsdb.de/

The original data are distributed under CC BY 4.0 (Attribution 4.0 International) https://creativecommons.org/licenses/by/4.0/deed.en

## Content

This repository contains:

- `waistline_bls_de.json`:
  converted database with food names in German ready for import into Waistline.
- `waistline_bls_de.json`:
  converted database with food names in English ready for import into Waistline.
- `bls_to_waistline.py`:
  a Python script that converts the BLS database (Microsoft Excel 2007+ format) into Waistline import format.

The conversion does the following:
- extreacts all default nutrition values used by Waistline (for complete list see python script) from BLS database
- keeps the original nutritional values
- only calories information is extracted, kilojouls information is not considered
- no information on selenium and caffeine as they are not included in BLS database
- trans-fat and omega-9-fat are summed up from severeal fatty acids (for details see source code of python script)
- when necessary amount is scaled to units used by Waistline
- changes the data format to JSON

## Import

In Waistline:
Settings → Import food database → Select JSON file

## Data license

The nutritional data are derived from:

Max Rubner-Institut (2025): Bundeslebensmittelschlüssel (BLS), Version 4.0. Karlsruhe.

The original data are available under CC BY 4.0 (Attribution 4.0 International).

## Disclaimer

This is an independent community project and is not affiliated with Max Rubner-Institut or the Waistline developers.

This repository only provides a conversion to the Waistline JSON format.
