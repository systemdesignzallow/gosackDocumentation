# Benchmarking Notes

## New Relic Results

![NewRelicScreenshot](./newRelicRandomQuery0.png)
New Relic Results

![ArtilleryCommands](./artilleryDemandWNewRelic.png)
Artillery Commands

Express is the current bottleneck.

## Artillery Commands and References

<https://artillery.io/docs/getting-started/>

```sh
artillery quick --count 100 -n 75 http://localhost:3001/test/
```