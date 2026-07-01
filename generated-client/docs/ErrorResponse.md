# ErrorResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**body** | [**ProblemDetail**](ProblemDetail.md) |  | [optional] [default to undefined]
**headers** | [**ErrorResponseHeaders**](ErrorResponseHeaders.md) |  | [optional] [default to undefined]
**statusCode** | [**HttpStatusCode**](HttpStatusCode.md) |  | [optional] [default to undefined]
**detailMessageArguments** | **Array&lt;object&gt;** |  | [optional] [default to undefined]
**typeMessageCode** | **string** |  | [optional] [default to undefined]
**detailMessageCode** | **string** |  | [optional] [default to undefined]
**titleMessageCode** | **string** |  | [optional] [default to undefined]

## Example

```typescript
import { ErrorResponse } from './api';

const instance: ErrorResponse = {
    body,
    headers,
    statusCode,
    detailMessageArguments,
    typeMessageCode,
    detailMessageCode,
    titleMessageCode,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
