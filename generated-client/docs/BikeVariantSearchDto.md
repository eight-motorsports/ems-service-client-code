# BikeVariantSearchDto

Request to search for a bike variant, model or make.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**makeId** | **number** | Id of motorcycle make | [default to undefined]
**modelId** | **number** | Id of motorcycle model | [optional] [default to undefined]
**year** | **number** | Year of motorcycle model. | [optional] [default to undefined]
**page** | **number** |  | [optional] [default to undefined]
**size** | **number** |  | [optional] [default to undefined]

## Example

```typescript
import { BikeVariantSearchDto } from './api';

const instance: BikeVariantSearchDto = {
    makeId,
    modelId,
    year,
    page,
    size,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
