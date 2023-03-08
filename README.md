# Grafana Plugins Playground

I use this for playing around with Grafana Plugins.

Right now I'm benchmarking frontend package managers.

Below are the outputs from `hyperfine "rm -rf ./node_modules/.cache && <insert_package_manager> run build" -r 5 --export-json ./<insert_package_manager>-build-run.json` which removes any webpack cache and builds the basic datasource plugin.

### NPM

```
Benchmark 1: rm -rf ./node_modules/.cache && npm run build
Time (mean ± σ):     11.732 s ±  0.704 s    [User: 18.073 s, System: 4.903 s]
Range (min … max):   11.075 s … 12.917 s    5 runs
```

### Yarn 1

```
Benchmark 1: rm -rf ./node_modules/.cache && yarn run build
Time (mean ± σ):     10.700 s ±  0.092 s    [User: 17.483 s, System: 4.222 s]
Range (min … max):   10.626 s … 10.856 s    5 runs
```

### PNPM

```
Benchmark 1: rm -rf ./node_modules/.cache && pnpm run build
Time (mean ± σ):      7.565 s ±  0.212 s    [User: 13.025 s, System: 3.016 s]
Range (min … max):    7.432 s …  7.940 s    5 runs
```