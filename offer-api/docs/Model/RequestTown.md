# RequestTown

The request that is expected to be sent to the [**Town-Request-API**](../Api/RequestTownApi.md).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**town_id** | **int** |  | 
**position** | [**Position**](Position.md) |  | [optional] 
**person_ages** | **int[]** | The ages of all people who want to book | 
**start_date** | [**\DateTime**](\DateTime.md) |  First day of booking consumation. Format: YYYY-MM-DD | 
**end_date** | [**\DateTime**](\DateTime.md) | Last day of booking consumation. Format: YYYY-MM-DD | 
**currency** | **string** | offer should be calculated. Available values: "EUR", "GBP", "USD", "CHF", 'PLN', 'CZK' | 
**offer_type** | **string** | Type of the offer | 
**language** | **string** | Language code of the expected product descriptions. Available values: "de", "en", "fr", "it", "nl", "pl", "cz", "sk", "dk", "es" | 

