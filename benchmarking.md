# Benchmarking Notes

## AWS Results

### New Relic

![NewRelicScreenshot](./newRelicServiceAWS.png)
New Relic Post Results

### Arillery Commands and Results

![ArtilleryCommands](./artilleryServiceAWS.png)
Artillery Commands

## New Relic Proxy Results

![NewRelicScreenshot](./newRelicProxyResults.png)
New Relic Post Results

![ArtilleryCommands](./proxyArtillery.png)
Artillery Commands

## New Relic Service Results

![NewRelicScreenshot](./newRelicPost.png)
New Relic Post Results

![NewRelicScreenshot](./newRelicNewArtillery.png)
New Relic Results (Round 2)

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
