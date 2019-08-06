# Benchmarking Notes

## EC2 Service Results with Loader.io

![NewRelic/Loader.io](./loaderio-newrelic.png)
New Relic EC2 Service Get Results Loaded by Loader.io

![Loader.io](./loaderio.png)
New Relic EC2 Service Get Results Loader.io Trends

## EC2 Proxy Results

![NewRelicScreenshot](./proxyEC2NewRelic.png)
New Relic EC2 Proxy Get Results

![ArtilleryCommands](./proxyEC2Artillery.png)
Artillery Commands

## EC2 Service Results

![NewRelicScreenshot](./newRelicServiceAWS.png)
New Relic Service EC2 Get Results

![ArtilleryCommands](./artilleryServiceAWS.png)
Artillery Commands

## New Relic Proxy Results (Local)

![NewRelicScreenshot](./newRelicProxyResults.png)
New Relic Get Local Results

![ArtilleryCommands](./proxyArtillery.png)
Artillery Commands

## New Relic Service Results (Local)

![NewRelicScreenshot](./newRelicPost.png)
New Relic Post Results

![NewRelicScreenshot](./newRelicNewArtillery.png)
New Relic Get Results (Round 2)

![NewRelicScreenshot](./newRelicRandomQuery0.png)
New Relic Get Results

![ArtilleryCommands](./artilleryDemandWNewRelic.png)
Artillery Commands

Express is the current bottleneck.

## Artillery Commands and References

<https://artillery.io/docs/getting-started/>

```sh
artillery quick --count 100 -n 75 http://localhost:3001/test/
```
