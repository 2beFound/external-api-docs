# Documentation for Master Data

All our APIs use the ALPINRESORTS.com ID system to reference towns and shops. Therefore, in order to 
address the APIs properly, you will have to retrieve the IDs through the Master Data API and create
mappings to your own ID system depending on your setup.   

## Authentication

The Master Data API uses an API key to authenticate you. It can be obtained from your sales contact. 
It is provided to the data as a GET-Parameter as part of the URL.

## Formats

Depending on your approach to process the information, the Master Data can be retrieved in 
spreadsheet-format through the [CSV](csv/README.md) endpoint, or in a hierarchical structure through the
[XML](xml/README.md) endpoint. Details on the contained information can be found in the respective README
files.
