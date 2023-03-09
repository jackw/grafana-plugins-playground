# Grafana Plugins Playground

I use this for playing around with Grafana Plugins.

Right now I'm benchmarking frontend package managers.

## Installs

### Cold

- NPM: `added 1738 packages, and audited 1739 packages in 3m`
- Yarn 1: `✨  Done in 77.48s.`
- PNPM: `Done in 44.1s`

### With lock file

- NPM: `added 1738 packages, and audited 1739 packages in 32s`
- Yarn 1: `✨  Done in 24.43s.`
- PNPM: `Done in 18.3s`

## Commands

All benchmarks are run on an i5-10th gen Macbook Pro (2020).

## `build`

Below are the outputs from `hyperfine --prepare "rm -rf ./node_modules/.cache" -r 8 --export-json "./bench-build.json" "<INSERT_PACKAGE_MANAGER> run build"` which removes any webpack cache between builds and builds the basic datasource plugin.

### NPM

```
Benchmark 1: npm run build
  Time (mean ± σ):     10.926 s ±  0.820 s    [User: 17.479 s, System: 4.392 s]
  Range (min … max):   10.490 s … 12.889 s    8 runs
```

### Yarn 1

```
Benchmark 1: yarn run build
  Time (mean ± σ):     10.973 s ±  0.787 s    [User: 17.728 s, System: 4.318 s]
  Range (min … max):   10.429 s … 12.692 s    8 runs
```

### PNPM

```
Benchmark 1: pnpm run build
  Time (mean ± σ):      7.197 s ±  0.472 s    [User: 11.898 s, System: 2.862 s]
  Range (min … max):    6.938 s …  8.347 s    8 runs
```

## `test:ci`

Below are the outputs from `hyperfine --prepare "<INSERT_PACKAGE_MANAGER> jest --clearCach" -r 8 --export-json "./bench-test.json" "<INSERT_PACKAGE_MANAGER> run test:ci"` which clears jest cache between test runs.

### NPM

```
Benchmark 1: npm run test:ci
  Time (mean ± σ):      2.198 s ±  0.233 s    [User: 2.287 s, System: 0.538 s]
  Range (min … max):    1.967 s …  2.655 s    8 runs
```

### Yarn 1

```
Benchmark 1: yarn run test:ci
  Time (mean ± σ):      1.794 s ±  0.226 s    [User: 1.845 s, System: 0.436 s]
  Range (min … max):    1.689 s …  2.349 s    8 runs
```

### PNPM

```
Benchmark 1: pnpm run test:ci
  Time (mean ± σ):      2.309 s ±  0.210 s    [User: 2.239 s, System: 0.636 s]
  Range (min … max):    2.181 s …  2.813 s    8 runs
```