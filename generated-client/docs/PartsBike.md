# PartsBike


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **number** |  | [optional] [default to undefined]
**vin** | **string** |  | [optional] [default to undefined]
**notes** | **string** |  | [optional] [default to undefined]
**partsCatalogUrl** | **string** |  | [optional] [default to undefined]
**mileage** | **number** |  | [optional] [default to undefined]
**countryOfOrigin** | **string** |  | [optional] [default to undefined]
**listingNameTemplate** | **string** |  | [optional] [default to undefined]
**listingDescriptionHtmlTemplate** | **string** |  | [optional] [default to undefined]
**photoUrls** | **Array&lt;string&gt;** |  | [optional] [default to undefined]
**thumbnailUrl** | **string** |  | [optional] [default to undefined]
**parts** | [**Array&lt;Part&gt;**](Part.md) |  | [optional] [default to undefined]
**bikeVariant** | [**BikeVariant**](BikeVariant.md) |  | [optional] [default to undefined]

## Example

```typescript
import { PartsBike } from './api';

const instance: PartsBike = {
    id,
    vin,
    notes,
    partsCatalogUrl,
    mileage,
    countryOfOrigin,
    listingNameTemplate,
    listingDescriptionHtmlTemplate,
    photoUrls,
    thumbnailUrl,
    parts,
    bikeVariant,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
