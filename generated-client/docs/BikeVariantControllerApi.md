# BikeVariantControllerApi

All URIs are relative to *http://ems-service-dev-317696638565.us-east4.run.app*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**deleteBikeVariant**](#deletebikevariant) | **DELETE** /api/bike-variant/{bikeVariantId} | Delete a bike variant|
|[**exportBikeVariants**](#exportbikevariants) | **GET** /api/bike-variant/export | Export bike variants to CSV|
|[**getAllMakes**](#getallmakes) | **GET** /api/bike-variant/all-makes | Get all motorcycle makes.|
|[**getBikeVariantYears**](#getbikevariantyears) | **GET** /api/bike-variant/get-years | Gets years of existing bike variants|
|[**getMakes**](#getmakes) | **GET** /api/bike-variant/makes | Get motorcycle makes by year|
|[**getModels**](#getmodels) | **GET** /api/bike-variant/makes/{makeId}/models | Get models from make by year|
|[**getVariants**](#getvariants) | **GET** /api/bike-variant/models/{modelId}/variants | Get variants from model by year|
|[**importBikeVariants**](#importbikevariants) | **POST** /api/bike-variant/import | Import bike variants from CSV|
|[**saveBikeVariant**](#savebikevariant) | **POST** /api/bike-variant | Create or update a bike variant|
|[**searchBikeVariant**](#searchbikevariant) | **POST** /api/bike-variant/search | Search bike variants|
|[**searchModels**](#searchmodels) | **GET** /api/bike-variant/models/search | Gets models based on search query.|
|[**uploadManual**](#uploadmanual) | **POST** /api/bike-variant/{bikeVariantId}/manual | Upload service manual PDF|

# **deleteBikeVariant**
> deleteBikeVariant()

Deletes a bike variant by id.  The bike variant id must exist. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let bikeVariantId: number; // (default to undefined)

const { status, data } = await apiInstance.deleteBikeVariant(
    bikeVariantId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **bikeVariantId** | [**number**] |  | defaults to undefined|


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
|**400** | Invalid bike variant id |  -  |
|**204** | Bike variant deleted successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **exportBikeVariants**
> File exportBikeVariants()

Exports all bike variants as a CSV file.  The export includes make, model and bike variant information. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

const { status, data } = await apiInstance.exportBikeVariants();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**File**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/csv, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Bike variants exported successfully |  -  |
|**400** | Export failure |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getAllMakes**
> Array<BasicBikeInfo> getAllMakes()

Returns a simplified list of all motorcycle makes.  This endpoint is intended for dropdowns and basic selection lists. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

const { status, data } = await apiInstance.getAllMakes();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**Array<BasicBikeInfo>**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid or missing year |  -  |
|**200** | Makes returned successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getBikeVariantYears**
> Array<number> getBikeVariantYears()

Gets years of existing bike variants 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

const { status, data } = await apiInstance.getBikeVariantYears();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**Array<number>**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Years returned successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getMakes**
> Array<BasicBikeInfo> getMakes()

Returns a simplified list of motorcycle makes that have at least one bike variant for the provided year.  This endpoint is intended for dropdowns and basic selection lists. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let year: number; // (default to undefined)

const { status, data } = await apiInstance.getMakes(
    year
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **year** | [**number**] |  | defaults to undefined|


### Return type

**Array<BasicBikeInfo>**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid or missing year |  -  |
|**200** | Makes returned successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getModels**
> Array<BasicBikeInfo> getModels()

Returns a simplified list of motorcycle models linked to a make that have at least one bike variant for the provided year.  This endpoint is intended for dropdowns and basic selection lists. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let makeId: number; // (default to undefined)
let year: number; // (default to undefined)

const { status, data } = await apiInstance.getModels(
    makeId,
    year
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **makeId** | [**number**] |  | defaults to undefined|
| **year** | [**number**] |  | defaults to undefined|


### Return type

**Array<BasicBikeInfo>**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Models returned successfully |  -  |
|**400** | Invalid make id or missing year |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getVariants**
> Array<BasicBikeInfo> getVariants()

Returns a simplified list of bike variants linked to a model for the provided year.  This endpoint is intended for dropdowns and basic selection lists. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let modelId: number; // (default to undefined)
let year: number; // (default to undefined)

const { status, data } = await apiInstance.getVariants(
    modelId,
    year
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **modelId** | [**number**] |  | defaults to undefined|
| **year** | [**number**] |  | defaults to undefined|


### Return type

**Array<BasicBikeInfo>**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid model id or missing year |  -  |
|**200** | Variants returned successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **importBikeVariants**
> BikeVariantImportResult importBikeVariants()

Imports bike variants from a CSV file.  The import can create models and bike variants.  Expected CSV headers may include:  make_id, make, model_id, model, bike_variant_id, year, variant, service_manual_url, cc, cylinder  Rules: - If bike_variant_id is provided, the existing bike variant is updated. - If bike_variant_id is not provided, a new bike variant is created. - If model_id is provided, the existing model is used. - If model_id is not provided, the model may be created using make_id and model. - make_id must reference an existing make when creating a model. - Existing duplicate variants are skipped. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let file: File; // (default to undefined)

const { status, data } = await apiInstance.importBikeVariants(
    file
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **file** | [**File**] |  | defaults to undefined|


### Return type

**BikeVariantImportResult**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid CSV file or import failure |  -  |
|**200** | Bike variants imported successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **saveBikeVariant**
> BikeVariant saveBikeVariant(saveBikeVariantDto)

Creates or updates a bike variant.  This endpoint can also create a motorcycle model when modelId is not provided.  Rules: - If bikeVariantId is provided, the existing bike variant is updated. - If bikeVariantId is not provided, a new bike variant is created. - If modelId is provided, the existing model is used. - If modelId is not provided, a new model is created using makeId and modelName. - makeId must reference an existing make when creating a new model. - Provided model and bike variant ids must exist. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration,
    SaveBikeVariantDto
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let saveBikeVariantDto: SaveBikeVariantDto; //

const { status, data } = await apiInstance.saveBikeVariant(
    saveBikeVariantDto
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **saveBikeVariantDto** | **SaveBikeVariantDto**|  | |


### Return type

**BikeVariant**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Bike variant saved successfully |  -  |
|**400** | Invalid bike variant payload |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **searchBikeVariant**
> Page searchBikeVariant(bikeVariantSearchDto)

Searches bike variants using optional filters.  Supported filters: - makeId - modelId - year  If a filter is empty, it is ignored. Paging is applied according to the provided Pageable object. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration,
    BikeVariantSearchDto
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let bikeVariantSearchDto: BikeVariantSearchDto; //

const { status, data } = await apiInstance.searchBikeVariant(
    bikeVariantSearchDto
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **bikeVariantSearchDto** | **BikeVariantSearchDto**|  | |


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
|**400** | Invalid search payload |  -  |
|**200** | Bike variants returned successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **searchModels**
> Array<BasicBikeInfo> searchModels()

Returns a simplified list of models.  This endpoint is intended for dropdowns and basic selection lists. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let makeId: number; // (default to undefined)
let query: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.searchModels(
    makeId,
    query
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **makeId** | [**number**] |  | defaults to undefined|
| **query** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Array<BasicBikeInfo>**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**400** | Invalid or missing field |  -  |
|**200** | Makes returned successfully |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **uploadManual**
> string uploadManual()

Uploads a PDF service manual for an existing bike variant.  Rules: - bikeVariantId must reference an existing bike variant. - The uploaded file must be a PDF. - The uploaded manual is stored in S3. - The bike variant\'s serviceManualUrl field is updated with the uploaded file URL. 

### Example

```typescript
import {
    BikeVariantControllerApi,
    Configuration
} from './api';

const configuration = new Configuration();
const apiInstance = new BikeVariantControllerApi(configuration);

let bikeVariantId: number; //ID of the bike variant to attach the manual to (default to undefined)
let manual: File; //PDF service manual file (default to undefined)

const { status, data } = await apiInstance.uploadManual(
    bikeVariantId,
    manual
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **bikeVariantId** | [**number**] | ID of the bike variant to attach the manual to | defaults to undefined|
| **manual** | [**File**] | PDF service manual file | defaults to undefined|


### Return type

**string**

### Authorization

[LicenseKey](../README.md#LicenseKey)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: text/plain, application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Service manual uploaded successfully |  -  |
|**400** | Invalid bike variant id, missing file, or invalid file type |  -  |
|**401** | Missing or invalid license key |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

