# ALPINRESORTS.com API documentation

## What it does

This API allows you to retrieve the offerings of ALPINRESORTS.com in a machine-readable format.

The **Master Data API** allows you to retrieve a list of all shops that are offered on ALPINRESORTS.com, including useful meta-information and example prices. 
Please refer to the docs of the [CSV](master-data-api/csv/README.md) and [XML](master-data-api/xml/README.md) versions, respectively.

The **Offer API** allows you to retrieve offers specifically for your customers' specifications regarding location, date and group constellation.
Please refer to the docs of the [REST](offer-api/README.md) API for details.

## What you need

To access the API, you will need the following credentails:

- To use the Master Data API, you need an `api-key`.
- To use the Offer API, you need `username` and `password`.

Please refer to your sales contact to obtain these credentials, or contact us at info@alpinresorts.com.

## How you start

### Get links to town pages

- Retrieve the master data in the format you want
- Create mappings between the ALPINRESORTS.com town-ID system and your own
- Display the links to the town pages with the URLs from the master data

### Get links to shop pages

- Retrieve the master data in the format you want
- Create mappings between the ALPINRESORTS.com shop-ID system and your own
- Display the links to the shops' "parameter" pages with the URLs from the master data. On that page, the client can enter 
the specifics of their booking.

### Get specific offers for a set of booking parameters

- Retrieve the master data in the format you want
- Create mappings between the ALPINRESORTS.com shop-ID system and your own
- Implement a client for the [Auth-API](offer-api/docs/Api/AuthApi.md).
- Implement a client for either the [Town-API](offer-api/docs/Api/RequestTownApi.md) or the [Shop-API](offer-api/docs/Api/RequestShopApi.md). 
- Display the details of the [Offers](offer-api/docs/Model/Offer.md) retrieved from the APIs.

