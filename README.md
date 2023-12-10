# TrustMark Previous Measure Checker (PMC) Integration

First Published December 23

## Introduction

The TrustMark Previous Measure Checker (PMC) is an API that is available to allow users to lookup measures that have been installed at a property by providing a Unique Property Reference Number (UPRN).

### Measures

The API will only return Lodged measures, meaning subsequent Lodgement Voids and Measure Amends will affect subsequent results, and point-in-time results will contain what is currently held with TrustMark.

Measures of the same `Measure Category` as defined in the TrustMark Data Dictionary will only return the latest.

## Prerequisites

You must request access to the API directly with TrustMark to obtain an API Key.

## API Endpoints

All API endpoints require an x-api-key which will be issued by TrustMark.

### POST /LookupUPRNs

This endpoint allows you to lookup by UPRN and return a list of measures that have been installed at the property. The endpoint requires a JSON body containing the UPRN to lookup which can contain an array of upto 1000 UPRN values.

#### Request

```json
{
  "UPRNs": [
    "100023336956",
  ]
}
```



## Environments

The API is available in the following environments:

| Environment | URL |
| ----------- | --- |
| UAT | https://api.uat.pmc.data-hub.org.uk |
| Production | https://api.pmc.data-hub.org.uk |

## Swagger

The Swagger documentation for the API is available at the following URLs:

| Environment | URL |
| ----------- | --- |
| UAT | https://api.uat.pmc.data-hub.org.uk/swagger/index.html |
| Production | https://api.pmc.data-hub.org.uk/swagger/index.html |
