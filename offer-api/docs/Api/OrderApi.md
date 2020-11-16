# OrderApi

All URIs are relative to *https://www.alpinresorts.com*

 HTTP request | Description
 ------------- | -------------
 **GET** /api/order/order_summaries | Retrieve a list of completed bookings. The list is limited to 30 entries use the optional page parameter to skip through.

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **string**| Used for pagination |

### Return type

[**OrderSummariesResponse**](../Model/OrderSummariesResponse.md)

### Example

[**Sample Request**](../../demo-requests/order-api.http)
