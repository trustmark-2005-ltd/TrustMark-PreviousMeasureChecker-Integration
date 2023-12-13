# TrustMark Previous Measure Checker (PMC) Integration

First Published December 23

## Introduction

The TrustMark Previous Measure Checker (PMC) is an API that is available to allow users to lookup measures that have been installed at a property by providing a Unique Property Reference Number (UPRN). This API is currently restricted to particular use cases and is not open for applications. 

### Measures

The API will only return Lodged measures, meaning subsequent Lodgement Voids and Measure Amends will affect subsequent results, and point-in-time results will contain what is currently held with TrustMark.

Measures of the same `Measure Category` as defined in the TrustMark Data Dictionary will only return the latest.

## Prerequisites

You must request access to the API directly with TrustMark to obtain an API Key.

## API Endpoints

All API endpoints require an x-api-key which will be issued by TrustMark.

### POST /LookupUPRNs

This endpoint allows you to lookup by UPRN and return a list of measures that have been installed at the property. The endpoint requires a JSON body containing the UPRN to lookup which can contain an array of upto 100 UPRN values.

#### Request

```json
{
  "UPRNs": [
    "100023336956",
  ]
}
```

#### Response

```json
{
  "results": [
    {
      "isSuccess": true,
      "exists": true,
      "uprn": "12345678",
      "address": {
        "postcode": "RG24 4EB",
        "address1": "TrustMark",
        "ladCode": "E07000084"
      },
      "propertyInformation": {
        "propertyType": "Flat",
        "propertyDetachment": "End-terrace",
        "propertyBedrooms": "3",
        "propertyAge": "B",
        "propetyConstruction": [
          "Conventional, not high-rise, not protected - cavity wall"
        ]
      },
      "measures": [
        {
          "measureCategory": "Cavity Wall Insulation",
          "measureType": "Cavity wall insulation (0.040)",
          "installedDate": "2023-09-28T00:00:00+00:00",
          "handoverDate": "2023-09-28T00:00:00+00:00",
          "certificateNumber": "P10527-1",
          "umr": "P105275634",
          "mcsCertificateNumber": null,
          "lodgementType": "ECO4",
          "trustmarkTradeCode": 91,
          "dwCode": "DW-101",
          "sapMeasureName": "tbc",
          "lodgedStatus": "Complete"
        }
      ]
    }
  ],
  "metadata": {
    "origin": "TrustMark",
    "service": "Previous Measure Checker (PMC)",
    "packageId": "e3323e18-407c-44f9-b876-e22527a0c34a",
    "version": "1.0",
    "dateCompiled": "2023-11-29",
    "lastUpdated": "2023-12-11",
    "personalData": "No",
    "permittedUse": [
      "PMC–Validation",
      "PMC-Marketing"
    ],
    "sharingBasis": "DSA",
    "attribution": "Includes data provided by TrustMark",
    "documentation": "https://github.com/trustmark-2005-ltd/TrustMark-PreviousMeasureChecker-Integration/"
  }
}
```

| Attribute | Note |
| ----------- | --- |
| isSuccess: true | indicates that the call was successful. |
| exists: true | indicates that data was found for this uprn. |

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

## Metadata

The data returned will contain metadata relating to the data provided and how it may be used.
