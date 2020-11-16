# CustomerData

The data of a customer making a booking using the [**Booking-API**](../Api/BookingApi.md).

## Properties

Name | Type | Description | Notes
------------ | ------------- | -------------| -------------
**orderId** | **integer** | The identifiert of this order.
**customerCountry** | **string** | ISO 3166-1 Alpha-2 country code of the customer's residence |
**customerCulture** | **string** | The ISO 639-1 language code used by the customer. Notice that only languages supported on ALPINRESORTS.com are accepted. 
**customerCurrencyCode** | **string** | The currency of this order.
**isSkihireItemPresent** | **boolean** | The order includes a ski-hire item.
**isSkihireAddonPresent** | **boolean** | The order includes addon items like boots or a helmet.
**isCancellationInsuranceItemPresent** | **boolean** | The includes a cancellation-insurance. 
**isInsuranceItemPresent** | **boolean** | The order includes a safety-insurance.
**isInsurancePlusItemPresent** | **boolean** | The order includes a safety-plus-insurance.
**start_date** | **string** | First day of booking consumation. Format: ISO-8601 | Example: "2020-12-24T00:00:00+00:00"
**start_date** | **string** | Last day of booking consumation. Format: ISO-8601 | Example: "2020-12-24T00:00:00+00:00"
**onlineTurnover** | **integer** |  Total amount in the given currency's subdivision (e.g. "10000" means 100 EUR) |  
**nameAbbreviated** | **string** | The customers name abbreviated: | Example: John D., Maria A.
