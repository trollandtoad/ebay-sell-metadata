# OpenAPIClient-php

The Metadata API has operations that retrieve configuration details pertaining to the different eBay marketplaces. In addition to marketplace information, the API also has operations that get information that helps sellers list items on eBay.


## Installation & Usage

### Requirements

PHP 7.2 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/AjohnsonCHC/EbaySellMetadata.git"
    }
  ],
  "require": {
    "AjohnsonCHC/EbaySellMetadata": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/OpenAPIClient-php/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure OAuth2 access token for authorization: api_auth
$config = eBay\Sell\Metadata\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new eBay\Sell\Metadata\Api\CountryApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$country_code = 'country_code_example'; // string | This path parameter specifies the two-letter ISO 3166-1 Alpha-2 country code for the country whose jurisdictions you want to retrieve. eBay provides sales tax jurisdiction information for Canada and the United States. Valid values for this path parameter are CA and US.

try {
    $result = $apiInstance->getSalesTaxJurisdictions($country_code);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CountryApi->getSalesTaxJurisdictions: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.ebay.com/sell/metadata/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CountryApi* | [**getSalesTaxJurisdictions**](docs/Api/CountryApi.md#getsalestaxjurisdictions) | **GET** /country/{countryCode}/sales_tax_jurisdiction | 
*MarketplaceApi* | [**getAutomotivePartsCompatibilityPolicies**](docs/Api/MarketplaceApi.md#getautomotivepartscompatibilitypolicies) | **GET** /marketplace/{marketplace_id}/get_automotive_parts_compatibility_policies | 
*MarketplaceApi* | [**getItemConditionPolicies**](docs/Api/MarketplaceApi.md#getitemconditionpolicies) | **GET** /marketplace/{marketplace_id}/get_item_condition_policies | 
*MarketplaceApi* | [**getListingStructurePolicies**](docs/Api/MarketplaceApi.md#getlistingstructurepolicies) | **GET** /marketplace/{marketplace_id}/get_listing_structure_policies | 
*MarketplaceApi* | [**getNegotiatedPricePolicies**](docs/Api/MarketplaceApi.md#getnegotiatedpricepolicies) | **GET** /marketplace/{marketplace_id}/get_negotiated_price_policies | 
*MarketplaceApi* | [**getProductAdoptionPolicies**](docs/Api/MarketplaceApi.md#getproductadoptionpolicies) | **GET** /marketplace/{marketplace_id}/get_product_adoption_policies | 
*MarketplaceApi* | [**getReturnPolicies**](docs/Api/MarketplaceApi.md#getreturnpolicies) | **GET** /marketplace/{marketplace_id}/get_return_policies | 

## Models

- [AutomotivePartsCompatibilityPolicy](docs/Model/AutomotivePartsCompatibilityPolicy.md)
- [AutomotivePartsCompatibilityPolicyResponse](docs/Model/AutomotivePartsCompatibilityPolicyResponse.md)
- [Error](docs/Model/Error.md)
- [ErrorParameter](docs/Model/ErrorParameter.md)
- [Exclusion](docs/Model/Exclusion.md)
- [ItemCondition](docs/Model/ItemCondition.md)
- [ItemConditionPolicy](docs/Model/ItemConditionPolicy.md)
- [ItemConditionPolicyResponse](docs/Model/ItemConditionPolicyResponse.md)
- [ListingStructurePolicy](docs/Model/ListingStructurePolicy.md)
- [ListingStructurePolicyResponse](docs/Model/ListingStructurePolicyResponse.md)
- [NegotiatedPricePolicy](docs/Model/NegotiatedPricePolicy.md)
- [NegotiatedPricePolicyResponse](docs/Model/NegotiatedPricePolicyResponse.md)
- [ProductAdoptionPolicy](docs/Model/ProductAdoptionPolicy.md)
- [ProductAdoptionPolicyResponse](docs/Model/ProductAdoptionPolicyResponse.md)
- [ReturnPolicy](docs/Model/ReturnPolicy.md)
- [ReturnPolicyDetails](docs/Model/ReturnPolicyDetails.md)
- [ReturnPolicyResponse](docs/Model/ReturnPolicyResponse.md)
- [SalesTaxJurisdiction](docs/Model/SalesTaxJurisdiction.md)
- [SalesTaxJurisdictions](docs/Model/SalesTaxJurisdictions.md)
- [TimeDuration](docs/Model/TimeDuration.md)

## Authorization

### api_auth

- **Type**: `OAuth`
- **Flow**: `application`
- **Authorization URL**: ``
- **Scopes**: 
    - **https://api.ebay.com/oauth/api_scope**: View public data from eBay

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `v1.3.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
