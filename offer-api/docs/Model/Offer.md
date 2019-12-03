# Offer

The offer that is returned by the [**Offer-API**](../Api/OfferApi.md).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | UUID of the offer | 
**total** | **int** | Total amount due in the given currency's subdivision (e.g. "10000" means 100 EUR) |  
**shop_id** | **int** | The ID of the shop according to the master data export | 
**currency** | **string** | Currency of the given total. |
**products** | [**OfferProducts[]**](OfferProducts.md) |  |  
