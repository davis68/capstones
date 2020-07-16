# Test-Driven Development

## Target Usage

```sh
$ python grab-stations.py > stations.txt
$ python grab-forecast.py < stations.txt > forecast.txt
$ python plot-forecast.py < forecast.txt
```

Urbana is 40.1097° N, 88.2042° W

```sh
$ python interp-forecast.py --lat=40.1 --lon=88.2 < forecast.txt
```
