# BookingApi

All URIs are relative to *https://www.alpinresorts.com*

 HTTP request | Description
 ------------- | -------------
 **POST** /api/offer/book | Makes a booking for an offer

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offerUuid** | **string**| The UUID of the offer that should be booked |
 **customerData** | [**CustomerData**](../Model/CustomerData.md)| The information about the customer making the booking |

### Return type

[**BookingResponse**](../Model/BookingResponse.md)

### Example

[**Sample Request**](../../demo-requests/booking-api.http)
