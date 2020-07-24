# OpenAPI\Client\Offer\BookingRequestApi

All URIs are relative to *https://www.alpinresorts.com*

 HTTP request | Description
 ------------- | -------------
 **POST** /api/offer/book | Books an offer

Books an offer

### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **request_data** | [**BookingRequest**](../Model/BookingRequest.md)| Data transfer object containing additional information which is required to book |

### Return type

[**InlineResponse200**](../Model/InlineResponse200.md)

### Authorization

[apiKey](../../README.md#apiKey)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json
