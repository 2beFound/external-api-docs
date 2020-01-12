## Documentation for API Endpoints

All URIs are relative to *https://www.alpinresorts.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*RequestTownApi* | [**postRequestCollection**](docs/Api/RequestTownApi.md#postrequestcollection) | **POST** /api/offer/town | Requests offers for a town and given parameters.
*RequestShopApi* | [**postRequestCollection**](docs/Api/RequestShopApi.md#postrequestcollection) | **POST** /api/offer/shop | Requests an offer for a shop given parameters.
*OfferApi* | [**getOfferItem**](docs/Api/OfferApi.md#getofferitem) | **GET** /api/offer/{uuid} | Retrieves details of an existing offer.


## Documentation for Models

 - [RequestTown](docs/Model/RequestTown.md)
 - [RequestShop](docs/Model/RequestShop.md)
 - [Offer](docs/Model/Offer.md)
 - [OfferProducts](docs/Model/OfferProducts.md)


## Authentication

Before you can use any of the API endpoints, you must obtain an authentication (JWT) token from the Auth API. 
See the [Sample Authentication Request](demo-requests/auth.http). 
The `token` that is given by this API must then be sent as a header in subsequent API calls in the format.

`Authorization: Bearer <TOKEN>`

See for example the [Sample Shop Offer Request](demo-requests/request-shop-api.http). 

## Creating a link to the ski hire booking system

With the information obtained from the [Offer](docs/Model/Offer.md), it is possible to create a direct link into the 
product selection application of ALPINRESORTS.com. The applicable GET endpoint is

`https://www.alpinresorts.com/<app-slug>/products`

`app-slug` is the translated module name of the ski hire module, which
determines the display language. According to the user culture, one of
the following values must be chosen:

- German (de): `de/skiverleih`
- English (en): `en/ski-rental`
- French (fr): `fr/location-ski`
- Italian (it): `it/noleggio-ski`
- Dutch (nl): `nl/skiverhuur`

The following GET-parameters can be appended to populate the customer data when entering the product selection:

`shopId` (int): ID of the shop

`startDate` (string): The first day of consumation. Format: YYYY-MM-DD

`endDate` (string): The last day of consumation. Format: YYYY-MM-DD

`personAges` (int[]): Array of the persons' ages at the first day of consumation. Notice that these values will only be
considered if the user's browser does not yet have a session with ALPINRESORTS.com; this is to ensure that a user's 
current cart configuration is not overwritten unintentionally when clicking a link while a booking is already in progress. 

Example:

`https://www.alpinresorts.com/en/ski-rental/products?shopId=136&startDate=2020-04-17&endDate=2020-04-18&personAges[]=36&personAges[]=13&personAges[]=6`
