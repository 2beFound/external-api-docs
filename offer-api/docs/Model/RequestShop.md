# Request

The request that is expected to be sent to the [**Shop-Request-API**](../Api/RequestShopApi.md).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**shop_id** | **int** | The ID of the shop in the ALPINRESORTS.com database, as retrieved from the master data API. | 
**person_ages** | **int[]** | The ages of all people who want to book | 
**start_date** | **string** | First day of booking consumation. Format: YYYY-MM-DD | 
**end_date** | **string** | Last day of booking consumation. Format: YYYY-MM-DD | 
**currency** | **string** | In which currency the offer should be calculated. Available values: "EUR", "GBP", "USD", "CHF" | 
**offer_type** | **string** | Type of the offer. Available values:  "defaultProduct", "highestQuality" | 
**language** | **string** | Language code of the expected product descriptions. Available values: "en", "fr", "de", "it", "nl" | 
