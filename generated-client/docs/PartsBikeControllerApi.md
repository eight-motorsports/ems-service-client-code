# PartsBikeControllerApi

All URIs are relative to *http://ems-service-dev-317696638565.us-east4.run.app*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**deletePartsBike**](#deletepartsbike) | **DELETE** /api/parts-bike/{id} | Delete parts bike|
|[**getPartsBikeDetails**](#getpartsbikedetails) | **GET** /api/parts-bike/{id} | Get parts bike details|
|[**savePartsBike**](#savepartsbike) | **POST** /api/parts-bike/save | Save parts bike|
|[**searchPartsBikes**](#searchpartsbikes) | **POST** /api/parts-bike/search | Search parts bikes|
|[**uploadPartsBikeImage**](#uploadpartsbikeimage) | **POST** /api/parts-bike/image/upload | Upload parts bike image|

# **deletePartsBike**
> deletePartsBike()

Deletes a parts bike by ID.  This removes the parts bike record from the database.  Current behavior: - The parts bike entity is deleted. - Uploaded S3 images are not deleted by this endpoint. - If image URLs are stored on the entity, those references are removed with the entity. 

### Example

```typescript
import {
    PartsBikeControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new PartsBikeControllerApi(configuration);

let id: number; //ID of the parts bike to delete (default to undefined)

const { status, data } = await apiInstance.deletePartsBike(
    id
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **id** | [**number**] | ID of the parts bike to delete | defaults to undefined|


### Return type

void (empty response body)

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Parts bike deleted successfully |  -  |
|**401** | Missing or invalid license key |  -  |
|**400** | Parts bike does not exist |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getPartsBikeDetails**
> PartsBikeViewModel getPartsBikeDetails()

Gets the full details for a single parts bike.  The returned view model includes: - Parts bike information - Linked bike variant ID - Make ID - Model ID - Year - Photo URLs - Thumbnail URL - Listing templates 

### Example

```typescript
import {
    PartsBikeControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new PartsBikeControllerApi(configuration);

let id: number; //ID of the parts bike to retrieve (default to undefined)

const { status, data } = await apiInstance.getPartsBikeDetails(
    id
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **id** | [**number**] | ID of the parts bike to retrieve | defaults to undefined|


### Return type

**PartsBikeViewModel**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**401** | Missing or invalid license key |  -  |
|**400** | Parts bike does not exist |  -  |
|**200** | Parts bike details retrieved successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **savePartsBike**
> number savePartsBike(savePartsBikeDto)

Creates or updates a parts bike.  Rules: - If id is null, a new parts bike is created. - If id is provided, the existing parts bike is updated. - bikeVariantId is required. - bikeVariantId must reference an existing bike variant. - photoUrls should contain URLs previously returned by the image upload endpoint. - thumbnailUrl can reference one of the uploaded image URLs. 

### Example

```typescript
import {
    PartsBikeControllerApi,
    Configuration,
    SavePartsBikeDto
} from './api';

const configuration = new Configuration();
const apiInstance = new PartsBikeControllerApi(configuration);

let savePartsBikeDto: SavePartsBikeDto; //

const { status, data } = await apiInstance.savePartsBike(
    savePartsBikeDto
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **savePartsBikeDto** | **SavePartsBikeDto**|  | |


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
|**400** | Invalid parts bike data or referenced bike variant does not exist |  -  |
|**401** | Missing or invalid license key |  -  |
|**200** | Parts bike saved successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **searchPartsBikes**
> Page searchPartsBikes(partBikeSearchDto)

Searches parts bikes using the provided search criteria.  Paging is applied using the page and size values from the request body.  This endpoint returns a paginated list of basic parts bike information. 

### Example

```typescript
import {
    PartsBikeControllerApi,
    Configuration,
    PartBikeSearchDto
} from './api';

const configuration = new Configuration();
const apiInstance = new PartsBikeControllerApi(configuration);

let partBikeSearchDto: PartBikeSearchDto; //

const { status, data } = await apiInstance.searchPartsBikes(
    partBikeSearchDto
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **partBikeSearchDto** | **PartBikeSearchDto**|  | |


### Return type

**Page**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid search request |  -  |
|**401** | Missing or invalid license key |  -  |
|**200** | Parts bikes searched successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **uploadPartsBikeImage**
> string uploadPartsBikeImage()

Uploads a single image for a parts bike workflow.  Accepted file types: - PNG - JPG - JPEG  This endpoint uploads the image to S3 and returns the uploaded image URL.  The returned URL can then be included in SavePartsBikeDto.photoUrls or SavePartsBikeDto.thumbnailUrl when creating or updating a parts bike. 

### Example

```typescript
import {
    PartsBikeControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new PartsBikeControllerApi(configuration);

let picture: File; //Image file to upload. Supported extensions: png, jpg, jpeg. (default to undefined)

const { status, data } = await apiInstance.uploadPartsBikeImage(
    picture
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **picture** | [**File**] | Image file to upload. Supported extensions: png, jpg, jpeg. | defaults to undefined|


### Return type

**string**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json, text/plain


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid image file or unsupported file type |  -  |
|**401** | Missing or invalid license key |  -  |
|**200** | Image uploaded successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

