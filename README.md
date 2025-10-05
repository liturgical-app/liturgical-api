[![main](https://github.com/liturgical-app/liturgical-api/actions/workflows/main.yaml/badge.svg)](https://github.com/liturgical-app/liturgical-api/actions/workflows/main.yaml)
<a><img src="./src/resources/coverage/coverage.svg"></a>

# Liturgical API
<a href="https://www.python.org/"><img src="https://img.shields.io/badge/python-2a3035?logo=python&logoColor=ffdd54"></a>
<a href="https://github.com/features/actions"><img src="https://img.shields.io/badge/github%20actions-%232a3035.svg?logo=githubactions&logoColor=skyblue"></a>
<a href="https://render.com/"><img src="https://img.shields.io/badge/Render-%232a3035.svg?logo=render&logoColor=green"></a>

Get Liturgical information for a given date.
This API server uses the [Liturgical Calendar](https://github.com/liturgical-app/liturgical-calendar) library.

This API can be self-hosted, or there is a free-to-use instance hosted at [api.liturgical.uk](https://api.liturgical.uk)

## Usage

This is a read-only API without any authentication. Syntax is simple - simply supply the date in `YYYY-MM-DD` format.

`https://api.liturgical.uk/<yyyy-mm-dd>`

```json
# curl https://api.liturgical.uk/2025-12-20
{
  "colour": "purple",
  "colourcode": "#664fa6",
  "date": "2025-12-20",
  "ember": 0,
  "name": "",
  "prec": 1,
  "season": "Advent",
  "season_url": "https://en.wikipedia.org/wiki/Advent",
  "week": "Advent 3",
  "weekno": 3
}
```

## Run Locally
- 🔧 `pip install -r src/app/requirements.txt`
- 🚀 `gunicorn src.app.app:app`

## Pull image

```console
docker pull ghcr.io/liturgical-app/liturgical-api:latest
```

- Stable releases are built as image tags, e.g. `1.0.0`
- The `latest` tag points to the latest stable release
- The `edge` tag is built from the latest commit to `main`

## Run

A [Helm chart](https://artifacthub.io/packages/helm/liturgical/liturgical-api)
is available for deploying on Kubernetes.

## Issues

[Issues](https://github.com/liturgical-app/liturgical-api/issues) should
be logged against this project for problems with the API only.
Problems relating to the calculations of dates, colours and the calendar of
feasts should be logged against the
[Liturgical Calendar](https://github.com/liturgical-app/liturgical-calendar/issues) library.

PRs are welcome, but should pass the Pylint tests.