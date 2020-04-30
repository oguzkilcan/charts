# Helm chart repository

I took [technosophos/tscharts](https://github.com/technosophos/tscharts) as reference 
to host the charts I developed via GitHub pages.

## How to use the repository

Simply run:
```bash
$ helm repo add oguzkilcan https://oguzkilcan.github.io/charts
```
and start browsing them:
```bash
$ helm search repo oguzkilcan
NAME           	CHART VERSION	APP VERSION          	DESCRIPTION
oguzkilcan/plex	0.1.5        	1.19.2.2737-b69929dab	Streaming app for movies, TV, music, web shows ...
...
```

## How to add a chart

In the project root

1. Package the chart
```bash
$ helm package stable/plex
```

2. Put the packaged chart under `docs/`.
```bash
mv plex-0.1.5.tgz docs
```

3. Re-index the charts in the `docs/` directory
```bash
$ helm repo index docs --url https://oguzkilcan.github.io/charts
```

4. Add both files, commit, push:
```bash
$ git add --all
$ git commit -m "Release plex v0.1.5"
$ git push
```
