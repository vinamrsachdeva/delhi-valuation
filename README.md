# delhi-valuation
The quest to know the worth of Earth under New Delhi (India).
## version 0.1.0 (*under development*)
- [rough-delhi-buildings.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/rough-delhi-buildings.py) extracts all buildings within the perimeter defined roughly (not exactly) by all buildings above 28.377060 degrees N, below 28.938108 degrees N, to the right of 76.722650 degrees E and to the left of 77.466205 degrees East, which is a quadrilateral within which the city resides (including some surrounding subrubs that will be eliminated from analysis after subsequent processes). In order to run it, download the [391_buildings.csv](https://storage.googleapis.com/open-buildings-data/v3/polygons_s2_level_4_gzip/391_buildings.csv.gz) file from Google's [Open Buildings dataset](https://sites.research.google/open-buildings/#download).
- [delhi-buildings.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/delhi-buildings.py) extracts all buildings within a perimeter I drew on [geojson.io](https://geojson.io/). All coordinates of the rough perimeter I drew are in [new-delhi-coordinates.json](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/new-delhi-coordinates.json).
- [address-look-up.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/address-look-up.py) iterates through all the buildings extracted from [delhi-buildings.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/delhi-buildings.py), requests a human-readable address from OpenStreetMap's Nominatim API's reverse geocoding address look-up feature and drops any addresses that are not in Delhi.
- [delhi_land_value.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/delhi-land-value.py) (*under development*) would iterate through all buildings from [address-look-up.py](https://github.com/vinamrsachdeva/delhi-valuation/blob/main/address-look-up.py), adjust for maximum ground coverage requirements of the government to figure out an adjusted land area and multiply all land areas with their assessed values published by the municipal government (called "circle rate" for a given area).

**Limitations:**
- It calculates the land value based on the circle rate which is itself a [bad estimate](https://www.thehindubusinessline.com/opinion/the-official-price-of-land-is-a-joke/article64592464.ece) (but it's a very good lower-bound estimate).
- It's not able to match the address retrieved by reverse geocoding to the circle rate area categories.
