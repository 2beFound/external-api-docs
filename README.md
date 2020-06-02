# ALPINRESORTS.com API documentation

## What it does

This API allows you to retrieve and book the offerings of ALPINRESORTS.com in a machine-readable format.

The **Master Data API** allows you to retrieve a list of all shops that are offered on ALPINRESORTS.com, including useful meta-information and example prices. 
Please refer to the docs of the [CSV](master-data-api/csv/README.md) and [XML](master-data-api/xml/README.md) versions, respectively.

The **Offer API** allows you to retrieve offers and make bookings specifically for your customers' specifications regarding location, date and group constellation.
Please refer to the docs of the [REST](offer-api/README.md) API for details.

## What you need

To **access the API**, you will need the following credentails:

- To use the Master Data API, you need an `api-key`.
- To use the Offer API, you need `username` and `password`.

In order to activate **referer tracking** when linking to ALPINRESORTS.com, make sure that a proper Referer configuration
has been set up for you in the ALPINRESORTS.com system.

Please refer to your sales contact to obtain these credentials and the Referer setup, or contact us at info@alpinresorts.com.

## How you start

This section will show the necessary steps for some common use cases of our API offerings.

In order to use the API, you will always have to import and map our master data:

- Make yourself familiar with the [Master Data API](master-data-api/README.md).
- Retrieve the master data in the format you want.
- Create mappings between the ALPINRESORTS.com ID system and your own.

### Use Case: Referer Partnership

If you want to create links to ALPINRESORTS.com as part of a link partnership with referer tracking, you probably want to:

- *Create links to landing pages for towns*: the links to the town pages with the URLs are found in the master data.
- *Create links to shop pages*: the links to the shops' "parameter" are also found in the master data. On that page, the client can enter 
the specifics of their booking and proceed to the shop's products and prices.

### Use Case: Get offers and prices for a customer's specific set of booking parameters

If you can provide some details of your customer's travel intentions, you can get a specific offer for these booking parameters
through the [Offer-API](offer-api/README.md):  

- Authenticate through the [Auth-API](offer-api/docs/Api/AuthApi.md).
- Make a request to the [Town-API](offer-api/docs/Api/RequestTownApi.md) or the [Shop-API](offer-api/docs/Api/RequestShopApi.md)
  to get an [Offers](offer-api/docs/Model/Offer.md).
- You can then present the offer to the customer and allow them to proceed to the ALPINRESORTS.com booking engine (see also "Referer 
  Partnership" above) or provide your own checkout and confirm the booking later through the "Booking API" (see below). 

### Use Case: Make a booking for an offer

If you provide your own checkout process and want to make a booking on behalf of your customer, you can do this through
the [Offer-API](offer-api/README.md) by performing these steps:

- Retrieve an offer for the customer's booking parameters, as described above.
- Make a request to the [Booking-API](offer-api/docs/Api/BookingApi.md), including the offer reference and the booking customer's details.
- Retrieve the booking metadata from the resulting status link and inform your customer about the booking details.
