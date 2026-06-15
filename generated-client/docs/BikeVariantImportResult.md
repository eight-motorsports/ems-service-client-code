# BikeVariantImportResult

Result of a bike variant CSV import.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**modelsCreated** | **number** |  | [optional] [default to undefined]
**variantsCreated** | **number** |  | [optional] [default to undefined]
**skipped** | **number** |  | [optional] [default to undefined]
**variantsUpdated** | **number** |  | [optional] [default to undefined]
**failed** | **number** |  | [optional] [default to undefined]
**errors** | **Array&lt;string&gt;** | List of row-level import errors or skipped-row explanations. | [optional] [default to undefined]

## Example

```typescript
import { BikeVariantImportResult } from './api';

const instance: BikeVariantImportResult = {
    modelsCreated,
    variantsCreated,
    skipped,
    variantsUpdated,
    failed,
    errors,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
