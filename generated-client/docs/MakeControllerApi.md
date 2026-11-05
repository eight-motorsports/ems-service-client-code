# MakeControllerApi

All URIs are relative to *http://ems-service-dev-317696638565.us-east4.run.app*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**createMake**](#createmake) | **POST** /api/make | Create a motorcycle make|

# **createMake**
> number createMake(makeRequest)

Creates a new motorcycle make, such as Honda, Kawasaki, Yamaha, Triumph, etc.

### Example

```typescript
import {
    MakeControllerApi,
    Configuration,
    MakeRequest
} from './api';

const configuration = new Configuration();
const apiInstance = new MakeControllerApi(configuration);

let makeRequest: MakeRequest; //

const { status, data } = await apiInstance.createMake(
    makeRequest
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **makeRequest** | **MakeRequest**|  | |


### Return type

**number**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid request body |  -  |
|**401** | Missing or invalid license key |  -  |
|**200** | Make created successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

