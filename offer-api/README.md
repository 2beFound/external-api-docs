# Documentation for API Endpoints

This API is used to retrieve offers from ALPINRESORTS.com for a specific set of customer parameters (group size, booking 
timeframe, location, ...). Optionally, these offers can also be booked through the API.

## Authentication

Before you can use any of the API endpoints, you must obtain an authentication (JWT) token from the Auth API. 
See the [Sample Authentication Request](demo-requests/auth.http). 
The `token` that is given by this API must then be sent as a header in subsequent API calls in the format.

`Authorization: Bearer <TOKEN>`

See for example the [Sample Shop Offer Request](demo-requests/request-shop-api.http). 

## Data Mapping

Towns and shops are identified using the ALPINRESORTS.com ID system. In order to use it, make yourself familiar with 
the [Master Data API](master-data-api/README.md) and create mappings between the ALPINRESORTS.com ID system and your own 
master data structure.

## Retrieving an offer for your customer's booking parameters

Depending on how you much you know about the customer's stay, you can use:

### Town-API
If you know to which town your customer is going, you probably want to retrieve a variety of offers within that town.
Do so through the [Town-API](docs/Api/RequestTownApi.md).
 
### Shop-API
If you know exactly which shop your customer wants to go to, you can get a more specific offer through the
[Shop-API](docs/Api/RequestShopApi.md).

## Creating a link to the ski hire booking system

If you want to direct an interested customer to ALPINRESORTS.com to make the booking, it is possible to create a direct 
link into the product selection application with the information obtained from the [Offer](docs/Model/Offer.md). The 
applicable GET endpoint is

`https://www.alpinresorts.com/<app-slug>/products`

`app-slug` is the translated module name of the ski hire module, which
determines the display language. According to the user culture, one of
the following values must be chosen:

- German (de): `de/skiverleih`
- English (en): `en/ski-rental`
- French (fr): `fr/location-ski`
- Italian (it): `it/noleggio-ski`
- Dutch (nl): `nl/skiverhuur`
- Slovak (sk): `sk/pozicovna-lyzi`
- Čeština (cs): `cs/pujcovna-lyzi`
- Polski (pl): `pl/wypozyczalnia-nart`
- Español (es): `es/alquiler-de-esquis`
- Dansk (da): `da/skileje`

The following GET-parameters can be appended to populate the customer data when entering the product selection:

`shopId` (int): ID of the shop

`startDate` (string): The first day of consumation. Format: YYYY-MM-DD

`endDate` (string): The last day of consumation. Format: YYYY-MM-DD

`personAges` (int[]): Array of the persons' ages at the first day of consumation. Notice that these values will only be
considered if the user's browser does not yet have a session with ALPINRESORTS.com; this is to ensure that a user's 
current cart configuration is not overwritten unintentionally when clicking a link while a booking is already in progress. 

Example:

`https://www.alpinresorts.com/en/ski-rental/products?shopId=136&startDate=2020-04-17&endDate=2020-04-18&personAges[]=36&personAges[]=13&personAges[]=6`

## Making a booking for your customer

If you want to provide your own checkout process and make the booking on behalf of your customer through our API as well,
you can use the [Booking-API](docs/Api/BookingApi.md). You have to reference the [Offer](docs/Model/Offer.md) that should
be booked, and add the customer's data that is necessary to complete the booking. 

ALPINRESORTS.com will then perform the booking. You can retrieve all necessary information about the booking through the 
Offer Status URL returned from the API, and can inform your customer about the details. 

The booking will be charged to you and settled at a later time according to your contract.

## List completed Bookings

In order to retrieve a list of previously completed bookings through your API-Integration you can use the [Order-API](docs/Api/OrderApi.md).
