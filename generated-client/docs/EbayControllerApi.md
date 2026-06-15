# EbayControllerApi

All URIs are relative to *http://ems-service-dev-317696638565.us-east4.run.app*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getLocations**](#getlocations) | **GET** /api/ebay/locations | |
|[**validateToken**](#validatetoken) | **GET** /api/ebay/account-deletion | |

# **getLocations**
> object getLocations()


### Example

```typescript
import {
    EbayControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new EbayControllerApi(configuration);

const { status, data } = await apiInstance.getLocations();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**object**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | OK |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **validateToken**
> { [key: string]: string; } validateToken()


### Example

```typescript
import {
    EbayControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new EbayControllerApi(configuration);

let challengeCode: string; // (default to undefined)

const { status, data } = await apiInstance.validateToken(
    challengeCode
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **challengeCode** | [**string**] |  | defaults to undefined|


### Return type

**{ [key: string]: string; }**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | OK |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

