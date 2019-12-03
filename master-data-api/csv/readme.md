API endpoint
================================

Notice: unless stated otherwise, URLs are expected to be retrieved using the HTTP method `GET`.

URL
--------------------------------

The CSV data export can be downloaded as a CSV document under

`https://www.alpinresorts.com/de/service/ski-rental/shop-data-export/{api-key}`

where `{api-key}` must be replaced with the API-Key that you received from your ALPINRESORTS.com representative.

CSV Format for Ski Hire Export
--------------------------------

### Identifier Columns and Internationalization

Since some of the attributes of the shops have different values in different languages, every line
in this export file represents a combination of a language and a shop on ALPINRESORTS.com

`id` is the ID in the ALPINRESORTS.com database. The `lang` column is the language of the current line's translation. 

A combination of `lang` and `id` is therefore unique within the file.

### Additional columns

Notice: columns with values that are the same in every language are called "universal" and marked with |U|. 
All other columns have values that are translated between languages. 

`country` |U|: 2-letter-ISO-code of the country

`province`: Name of the town's province

`town_id` |U|: ID of the town in the ALPINRESORTS.com database

`town` |U|: Name of the town. Notice that this is intentionally a universal field. ALPINRESORTS.com uses the most common 
translation for all languages, even for towns that may be called differently in different languages  

`name` |U|: Name of the shop

`street` |U|: Street and number of the shop. If it is actually just a material delivery address,
 this column contains the text "Material delivery to the accommodation" or "Hotel-Shop-Shuttle-Service" 
 in its respective language version.

Geo-coordinates use the same convention as it is used by Google Maps:
- `longitude` |U|: larger than 0 -> eastern longitude, less than 0 ->
western longitude.
- `latitude` |U|: larger than 0 -> northern latitude, less than 0 ->
southern latitude.

`link_to_town`: URL of the ski hire town overview page on ALPINRESORTS.com that contains the shop.

`link_to_shop`: URL of the entry point into the shop's booking system of ALPINRESORTS.com for this shop.

`link_to_small_shop_image`/`link_to_big_shop_image`: URL of the shop's main image on ALPINRESORTS.com, in its two available sizes.

Furthermore, there is a sample offer from our website included in every line: 
- `sample_discount_period`: The reference timeframe during which the offer is valid.
- `sample_discount_percentage`: The discount percentage offered on ALPINRESORTS.com, in float format. E.g. 0.10 is for a 10% discount.
