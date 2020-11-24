# eBay\Sell\Metadata\MarketplaceApi

All URIs are relative to https://api.ebay.com/sell/metadata/v1.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getAutomotivePartsCompatibilityPolicies()**](MarketplaceApi.md#getAutomotivePartsCompatibilityPolicies) | **GET** /marketplace/{marketplace_id}/get_automotive_parts_compatibility_policies | 
[**getItemConditionPolicies()**](MarketplaceApi.md#getItemConditionPolicies) | **GET** /marketplace/{marketplace_id}/get_item_condition_policies | 
[**getListingStructurePolicies()**](MarketplaceApi.md#getListingStructurePolicies) | **GET** /marketplace/{marketplace_id}/get_listing_structure_policies | 
[**getNegotiatedPricePolicies()**](MarketplaceApi.md#getNegotiatedPricePolicies) | **GET** /marketplace/{marketplace_id}/get_negotiated_price_policies | 
[**getProductAdoptionPolicies()**](MarketplaceApi.md#getProductAdoptionPolicies) | **GET** /marketplace/{marketplace_id}/get_product_adoption_policies | 
[**getReturnPolicies()**](MarketplaceApi.md#getReturnPolicies) | **GET** /marketplace/{marketplace_id}/get_return_policies | 


## `getAutomotivePartsCompatibilityPolicies()`

```php
getAutomotivePartsCompatibilityPolicies($marketplace_id, $filter): \eBay\Sell\Metadata\Model\AutomotivePartsCompatibilityPolicyResponse
```



This method returns the eBay policies that a seller must adhere to when creating listings enabled with parts compatibility. By using the Parts Compatiblity feature, a seller is able to tell prospective buyers whether an automotive part or accessory item will fit their specific vehicle. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. See the Parts Compatibility Listings page for more information about how Parts Compatibility works when creating listings. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. Note: Only the following eBay marketplaces support automotive parts compatibility: EBAY_US EBAY_AU EBAY_CA EBAY_DE EBAY_ES EBAY_FR EBAY_GB EBAY_IT
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getAutomotivePartsCompatibilityPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getAutomotivePartsCompatibilityPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. Note: Only the following eBay marketplaces support automotive parts compatibility: EBAY_US EBAY_AU EBAY_CA EBAY_DE EBAY_ES EBAY_FR EBAY_GB EBAY_IT |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\eBay\Sell\Metadata\Model\AutomotivePartsCompatibilityPolicyResponse**](../Model/AutomotivePartsCompatibilityPolicyResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getItemConditionPolicies()`

```php
getItemConditionPolicies($marketplace_id, $filter): \eBay\Sell\Metadata\Model\ItemConditionPolicyResponse
```



This method returns the eBay policies that define how to specify item conditions in the categories of a specific marketplace. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getItemConditionPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getItemConditionPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\eBay\Sell\Metadata\Model\ItemConditionPolicyResponse**](../Model/ItemConditionPolicyResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getListingStructurePolicies()`

```php
getListingStructurePolicies($marketplace_id, $filter): \eBay\Sell\Metadata\Model\ListingStructurePolicyResponse
```



This method returns the eBay policies that define the allowed listing structures for the categories of a specific marketplace. The listing-structure policies currently pertain to whether or not you can list items with variations. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getListingStructurePolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getListingStructurePolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\eBay\Sell\Metadata\Model\ListingStructurePolicyResponse**](../Model/ListingStructurePolicyResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getNegotiatedPricePolicies()`

```php
getNegotiatedPricePolicies($marketplace_id, $filter): \eBay\Sell\Metadata\Model\NegotiatedPricePolicyResponse
```



This method returns the eBay policies that define the supported negotiated price features (like &quot;best offer&quot;) for the categories of a specific marketplace. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getNegotiatedPricePolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getNegotiatedPricePolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\eBay\Sell\Metadata\Model\NegotiatedPricePolicyResponse**](../Model/NegotiatedPricePolicyResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getProductAdoptionPolicies()`

```php
getProductAdoptionPolicies($marketplace_id, $filter): \eBay\Sell\Metadata\Model\ProductAdoptionPolicyResponse
```



This method retrieves a list of leaf categories for a marketplace and identifies the categories that require items to have an eBay product ID value in order to be listed in those categories. An eBay product ID value (known as an &quot;ePID&quot;) is a value that references a specific product in the eBay Catalog. Note: This method supports the eBay Product Based Shopping Experience (PBSE), which is applicable to only the US, UK, AU, and CA (English) marketplaces. Note that you can also use GetCategoryFeatures in the Trading API to retrieve similar information. For more information about using this method with PBSE, see the Product-Based Shopping Experience Playbook. Use the marketplace_id path parameter to specify the marketplace you want to review and use the filter query parameter to limit the categories returned in the response. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getProductAdoptionPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getProductAdoptionPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\eBay\Sell\Metadata\Model\ProductAdoptionPolicyResponse**](../Model/ProductAdoptionPolicyResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getReturnPolicies()`

```php
getReturnPolicies($marketplace_id, $filter): \eBay\Sell\Metadata\Model\ReturnPolicyResponse
```



This method returns the eBay policies that define whether or not you must include a return policy for the items you list in the categories of a specific marketplace, plus the guidelines for creating domestic and international return policies in the different eBay categories. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can return a very large response payload and we strongly recommend you get the results from this call in a GZIP file by including the following HTTP header with your request: &nbsp;&nbsp;Accept-Encoding: application/gzip

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Metadata\Api\MarketplaceApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$marketplace_id = 'marketplace_id_example'; // string | This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components.
$filter = 'filter_example'; // string | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character ('|'). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter=categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &nbsp;&nbsp;filter=categoryIds%3A%7B100%7C101%7C102%7D

try {
    $result = $apiInstance->getReturnPolicies($marketplace_id, $filter);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MarketplaceApi->getReturnPolicies: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_id** | **string**| This path parameter specifies the eBay marketplace for which policy information is retrieved. See the following page for a list of valid eBay marketplace IDs: Request components. |
 **filter** | **string**| This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent node, plus the policies for any leaf nodes below that parent node. The parameter takes a list of categoryId values and you can specify up to 50 separate category IDs. Separate multiple values with a pipe character (&#39;|&#39;). If you specify more than 50 categoryId values, eBay returns the policies for the first 50 IDs and a warning that not all categories were returned. Example: filter&#x3D;categoryIds:{100|101|102} Note that you must URL-encode the parameter list, which results in the following filter for the above example: &amp;nbsp;&amp;nbsp;filter&#x3D;categoryIds%3A%7B100%7C101%7C102%7D | [optional]

### Return type

[**\eBay\Sell\Metadata\Model\ReturnPolicyResponse**](../Model/ReturnPolicyResponse.md)

### Authorization

[api_auth](../../README.md#api_auth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
