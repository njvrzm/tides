# Proof of concept tide scraper

Scrapes https://www.tide-forecast.com/ for tide info for several fixed locations. By default, prints info for any low tides during daylight hours.

**Note: Python 3 is required.**

## Setup

`$ pip install -r requirements.txt`

## Demo

```bash
njv@nebulosa:~/Code/lowtide (master)$ python tides.py
Half Moon Bay, CA       low     08:37AM 3.3 ft
njv@nebulosa:~/Code/lowtide (master)$ python tides.py  --no_filter
Half Moon Bay, CA               high    03:46AM 4.42 ft
Half Moon Bay, CA               low     08:37AM 3.3 ft
Half Moon Bay, CA               high    02:01PM 4.97 ft
# etc.
```

## Usage

```python
from tides import get_tides_for_location

for tide in get_tides_for_location('huntington_beach'):
	# do something
```

## Notes

This is strictly proof-of-concept quality, although it could be used as is in another project that was itself a prototype. Some things I'd probably do next if I were continuing to work on it:

* More refactoring. There's quite a bit of repetition in `get_daylight_tides_from_html`, for example.
* Convert location info from dictionaries to data classes.
* Investigate the feasibility of providing an interface to the site's location lookup.
* Consider returning results as objects rather than dicts, and moving `is_daylight` and `is_low_tide` into properties.
