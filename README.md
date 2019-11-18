# Proof of concept tide scraper

Scrapes https://www.tide-forecast.com/ for tide info for several fixed locations. By default, prints info for any low tides during daylight hours.

## Setup

`$ pip install -r requirements.txt`

## Demo

```bash
njv@nebulosa:~/Code/lowtide (master)$ python tides.py
Half Moon Bay, CA       low     08:37AM 3.3 ft
```

## To use

```python
from tides import get_tides_for_location

for tide in get_tides_for_location('huntington_beach'):
	# do something
```
