---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the NUS Bus API! You can use the API to access NUS Bus API endpoints, which can get information on the bus stops and bus schedules available in the campus.

Feel free to make changes to improve the documentation or feedback if the APIs are not working.

# Base URL
All URLs referenced in the documentation have the following base:

`https://nextbus.comfortdelgro.com.sg/eventservice.svc`

# Bus Stops

## List All Stops

```shell
curl "https://nextbus.comfortdelgro.com.sg/eventservice.svc/BusStops"
```

> The above command returns JSON structured like this:

```json
{
  "BusStopsResult": {
    "busstops": [
      {
        "caption": "AS5",
        "latitude": 1.2936110496521,
        "longitude": 103.771942138672,
        "name": "AS7"
      },
      {
        "caption": "BIZ 2",
        "latitude": 1.29333997411937,
        "longitude": 103.775159716606,
        "name": "BIZ2"
      }
    ]
  }
}
```

This endpoint list all the bus stops and metadata such as GPS Coordinates.

### HTTP Request

`GET /BusStops`

# Bus Schedules

## Get a specific bus stop schedule

```shell
curl "https://nextbus.comfortdelgro.com.sg/eventservice.svc/Shuttleservice?busstopname=AS7"
```

> The above command returns JSON structured like this:

```json
{
  "ShuttleServiceResult": {
    "caption": "AS5",
    "name": "AS7",
    "shuttles": [
      {
        "arrivalTime": "5",
        "name": "A1",
        "nextArrivalTime": "12",
        "nextPassengers": "-",
        "passengers": "-"
      },
      {
        "arrivalTime": "7",
        "name": "D1",
        "nextArrivalTime": "14",
        "nextPassengers": "-",
        "passengers": "-"
      }
    ]
  }
}
```

This endpoint retrieves the specific schedule of a bus stop.

### HTTP Request

`GET /Shuttleservice?busstopname=<Name>`

### Query Parameters

Parameter | Description
--------- | -----------
Name | The name of the bus stop to retrieve e.g. `AS7`
