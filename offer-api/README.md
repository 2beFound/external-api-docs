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
