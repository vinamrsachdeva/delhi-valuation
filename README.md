# delhi-valuation
The quest to know the worth of Earth under New Delhi (India).
## version 0.1.0 (*under development*)
- [rough-delhi-lots.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/rough-delhi-lots.py) extracts all lots within the perimeter defined roughly (not exactly) by all lots above 28.377060 degrees N, below 28.938108 degrees N, to the right of 76.722650 degrees E and to the left of 77.466205 degrees East, which is a rough square around Delhi. In order to run it, download the [391_buildings.csv](https://storage.googleapis.com/open-buildings-data/v3/polygons_s2_level_4_gzip/391_buildings.csv.gz) file from Google's [Open Buildings dataset](https://sites.research.google/open-buildings/#download).
- [delhi-lots.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/delhi-lots.py) extracts all lots within a perimeter I drew on [geojson.io](https://geojson.io/). All coordinates of the rough perimeter I drew are in [new-delhi-coordinates.json](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/new-delhi-coordinates.json).
- [address-look-up.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/address-look-up.py) iterates through all the lots extracted from [delhi-lots.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/delhi-lots.py), requests a human-readable address from OpenStreetMap's Nominatim API's reverse geocoding address look-up feature and drops any addresses that are not in Delhi.
- An automated valuation model (*under development*).
- delhi_lot_value.py (*under development*) would iterate through all lots from [address-look-up.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/address-look-up.py), adjust for maximum ground coverage requirements of the government to figure out an adjusted lot area and multiply all lot areas with their (1) circle rates published by the government and (2) a rate estimated by the automated valuation model.
