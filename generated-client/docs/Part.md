# Part


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **number** |  | [optional] [default to undefined]
**partName** | **string** |  | [optional] [default to undefined]
**packageWidth** | **number** |  | [optional] [default to undefined]
**packageHeight** | **number** |  | [optional] [default to undefined]
**packageLength** | **number** |  | [optional] [default to undefined]
**packageWeight** | **number** |  | [optional] [default to undefined]
**partNumber** | **string** |  | [optional] [default to undefined]
**price** | **number** |  | [optional] [default to undefined]
**thumbnailUrl** | **string** |  | [optional] [default to undefined]
**status** | **string** |  | [optional] [default to undefined]
**partsBike** | [**PartsBike**](PartsBike.md) |  | [optional] [default to undefined]
**compatibleBikeVariants** | [**Set&lt;BikeVariant&gt;**](BikeVariant.md) |  | [optional] [default to undefined]
**extraParts** | **{ [key: string]: string; }** |  | [optional] [default to undefined]
**photoUrls** | **{ [key: string]: string; }** |  | [optional] [default to undefined]

## Example

```typescript
import { Part } from './api';

const instance: Part = {
    id,
    partName,
    packageWidth,
    packageHeight,
    packageLength,
    packageWeight,
    partNumber,
    price,
    thumbnailUrl,
    status,
    partsBike,
    compatibleBikeVariants,
    extraParts,
    photoUrls,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
