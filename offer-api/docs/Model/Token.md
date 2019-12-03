# Token

The authentication token that is returned by the [**Auth-API**](../Api/AuthApi.md).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**token** | **string** | The authentication token. | This token is an encrypted JWT token that expires after a given time. It must be passed to the other APIs with an `Authorization: Bearer` header | 
