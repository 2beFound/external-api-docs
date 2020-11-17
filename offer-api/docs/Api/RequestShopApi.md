# RequestTownApi

All URIs are relative to *https://www.alpinresorts.com*

HTTP request | Description
------------- | ------------- |
**POST** /api/offer/shop | Requests an offer for a given shop

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **request** | [**RequestShop**](../Model/RequestShop.md)| Data transfer object containing the offer parameters |

### Return type

[**Offer**](../Model/Offer.md)

### Example

[**Sample Request**](../../demo-requests/request-shop-api.http)
[**Sample Request, Limiting Additional Products**](../../demo-requests/request-shop-api-with-helmets-only.http)
[**Sample Request, Limiting Additional Products Strictly**](../../demo-requests/request-shop-api-with-helmets-only-strict.http)
[**Sample Request, Without Additional Products**](../../demo-requests/request-shop-api-with-no-additional-products.http)
