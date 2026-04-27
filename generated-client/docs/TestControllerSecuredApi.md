# TestControllerSecuredApi

All URIs are relative to *http://ems-service-dev-317696638565.us-east4.run.app*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getParts**](#getparts) | **GET** /api/test | |

# **getParts**
> string getParts()


### Example

```typescript
import {
    TestControllerSecuredApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new TestControllerSecuredApi(configuration);

const { status, data } = await apiInstance.getParts();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**string**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | OK |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

