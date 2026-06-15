# EbayAuthControllerApi

All URIs are relative to *http://ems-service-dev-317696638565.us-east4.run.app*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**callback**](#callback) | **GET** /api/ebay/auth/callback | |
|[**getAuthorizationUrl**](#getauthorizationurl) | **GET** /api/ebay/auth/url | |

# **callback**
> EbayToken callback()


### Example

```typescript
import {
    EbayAuthControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new EbayAuthControllerApi(configuration);

let code: string; // (default to undefined)

const { status, data } = await apiInstance.callback(
    code
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **code** | [**string**] |  | defaults to undefined|


### Return type

**EbayToken**

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

# **getAuthorizationUrl**
> string getAuthorizationUrl()


### Example

```typescript
import {
    EbayAuthControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new EbayAuthControllerApi(configuration);

const { status, data } = await apiInstance.getAuthorizationUrl();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**string**

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

