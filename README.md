# ALPINRESORTS.com API documentation

## What it does

This API allows you to retrieve and book the offerings of ALPINRESORTS.com in a machine-readable format.

The **Master Data API** allows you to retrieve a list of all shops that are offered on ALPINRESORTS.com, including useful meta-information and example prices. 
Please refer to the docs of the [CSV](master-data-api/csv/README.md) and [XML](master-data-api/xml/README.md) versions, respectively.

The **Offer API** allows you to retrieve offers and make bookings specifically for your customers' specifications regarding location, date and group constellation.
Please refer to the docs of the [REST](offer-api/README.md) API for details.

## How you start

### Pick your implementation scenario

An overview of some common use cases of our API offerings can be found in the [Scenarios section](scenarios/README.md).

### Acquire access credentials

To **access the API**, you will need the following credentails:

- To use the Master Data API, you need an `api-key`.
- To use the Offer API, you need `username` and `password`.

In order to activate **referer tracking** when linking to ALPINRESORTS.com, make sure that a proper Referer configuration
has been set up for you in the ALPINRESORTS.com system.

Please refer to your sales contact to obtain these credentials and the Referer setup, or contact us at info@alpinresorts.com.

### Map the master data
 
In order to use the API, you will always have to import and map the ALPINRESORTS.com master data so your system understands
which entities in your database should lead to which of the ALPINRESORTS.com offerings.

- Make yourself familiar with the [Master Data API](master-data-api/README.md).
- Retrieve the master data in the format you want.
- Create mappings between the ALPINRESORTS.com ID system and your own.
