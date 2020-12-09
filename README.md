# pyNowDawn

![Windows Build Status](https://github.com/Now-Dawn/pyNowDawn/workflows/Windows/badge.svg)
![Linux Build Status](https://github.com/Now-Dawn/pyNowDawn/workflows/Linux/badge.svg)
![MIT License](https://img.shields.io/github/license/Now-dawn/pyNowDawn)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FNow-Dawn%2FpyNowDawn.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2FNow-Dawn%2FpyNowDawn?ref=badge_shield)

## Open Source Python library for interfacing with the NowDawn API

## What is it?

PyNowDawn is a client Python wrapper library for NowDawn web APIs. It allows quick and easy consumption of NowDawn data by Python applications.

## Get started

### API key

As NowDawns APIs need a valid API key to allow responses, *PyNowDawn will not work without one*.
You can get a free API key [on the NowDawn website](https://nowdawn.com/sign_up)
Do note that free API subscription plans are subject to requests throttling.

### Example

With a free NowDawn API Key:

```python
from nowdawn import NowDawn as weatherBy

NowDawn('your-API-key')  # You MUST provide a valid API key

# Search for current weather in San Francisco (United States)
current_weather = weatherBy.city(city='San Francisco', country='US')  # Defaults to current weather measurement
print(current_weather)

# Weather details
current_weather.temperature     # 9
current_weather.humidity        # 87
current_weather.wind            # 4
current_weather.wind.direction  # 180

print(current_weather.__readings__)

# Get the current weather at lat=43.65N, lon=79.38W (Toronto, Canada)
observation = weatherBy.lat_lon(lat=43.65, lon=-79.38,
                               metric_units=False).forecast(plus_hour=1)
print(observation)
```

##  Installation

Install with `pip` for your ease:

```shell
$ pip install pyNowDawn
```

## Documentation

The library software API documentation is available on [Read the Docs](https://pynowdawn.readthedocs.io/en/latest/).


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FNow-Dawn%2FpyNowDawn.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2FNow-Dawn%2FpyNowDawn?ref=badge_large)