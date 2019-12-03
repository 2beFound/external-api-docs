API endpoint
================================

Notice: unless stated otherwise, URLs are expected to be retrieved using the HTTP method `GET`.

URL
--------------------------------

The XML data export can be downloaded as an XML document under

`https://www.alpinresorts.com/de/service/ski-rental/shop-list-export/{api-key}`

where `{api-key}` must be replaced with the API-Key that you received from your ALPINRESORTS.com representative.

XML Format for Ski Hire Export
--------------------------------

The basic hierarchy is:

- Envelope
    `->listShopsResponse->listShopsSuccess`
  - List of countries
    `->countries->country`
    - List of provinces
    `->provinces->province`
      - List of towns
      `->towns->town`
        - List of shops
        `->shops->shop`

Every singular corresponds to an entity in our database, the `id` is the
ID in our database and therefore unique. Most entities have multiple
`name`-tags which have a `lang` attribute, containing the translation of
the name into that language. If a `name` contains no `lang`, then the
name is universal (does not need to be translated).

`town` and `shop` also contain a `slug`, which is the descriptor of the
entity, processed for use in a URL (special characters removed,
lower-cased, ...). For example, an entity with a `name` of "Kärnten" gets a `slug` of "kaernten".

`imageUrl` is a path relative to https://www.alpinresorts.com/, e.g.
https://www.alpinresorts.com/uploads/images/alpinshop/small/a0ad4a71a30d719d0fb4085c59eaed0a0e867399.jpg

Geo-coordinates use the same convention as it is used by Google Maps:
- `longitude`: larger than 0 -> eastern longitude, less than 0 ->
western longitude.
- `latitude`: larger than 0 -> northern latitude, less than 0 ->
southern latitude.

`offer` is a sample offer from our website. The reference time is stated in the `start_date` and `end_date` attributes. `discount` is the discount percentage, `price` is the discounted ALPINRESORTS.com online price.

The remaining tags in `shop` should be self-explanatory.

Creating links to ALPINRESORTS.com from the export data
==================================================

Creating a link to the ski hire town overview
--------------------------------------------------

The overview page of a town's offerings can 
be created from the information given in the data export
using the following schema:

`https://www.alpinresorts.com/<app-slug>/{town-slug}`

The parameters mentioned are:

`app-slug` is the translated module name of the ski hire module, which
determines the display language. According to the user culture, one of
the following values must be chosen:

- German (de): `de/skiverleih`
- English (en): `en/ski-rental`
- French (fr): `fr/location-ski`
- Italian (it): `it/noleggio-ski`
- Dutch (nl): `nl/skiverhuur`

`town-slug` is the value in the export at the desired`town`'s `slug` tag with the desired `lang` attribute.

For example, consider this `town` entry: 

```
<town id="1">
    <name>Semmering</name>
    <slug lang="de">oesterreich/niederoesterreich/semmering</slug>
    <slug lang="en">austria/lower-austria/semmering</slug>
    <slug lang="fr">autriche/basse-autriche/semmering</slug>
    <slug lang="it">austria/bassa-austria/semmering</slug>
    <slug lang="nl">oostenrijk/neder-oostenrijk/semmering</slug>
    <shops>...</shops>
```

The `en` version of the town offering page can be found at   

https://www.alpinresorts.com/en/ski-rental/austria/lower-austria/semmering

Creating a link to the ski hire booking system
--------------------------------------------------

To enter the booking system of ALPINRESORTS.com, entry of booking
parameters is required. The form for entry of this information can 
be created from the information given in the data export
using the following schema:

`https://www.alpinresorts.com/<app-slug>/parameters/{shop-id}`

The parameters mentioned are:

`app-slug` is the translated module name of the ski hire module, which
determines the display language. According to the user culture, one of
the following values must be chosen:

- German (de): `de/skiverleih`
- English (en): `en/ski-rental`
- French (fr): `fr/location-ski`
- Italian (it): `it/noleggio-ski`
- Dutch (nl): `nl/skiverhuur`

`shop-id` is the `id`-value for the given `shop`-tag.
 
For example, for a `shop` with `id`=2030, the `en` entry page to ALPINRESORTS.com would be

https://www.alpinresorts.com/en/ski-rental/parameters/2030
