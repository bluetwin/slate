# Lawyers

Get single, bulk, or search for Avvo lawyers.

> Example response

```json
{

  "lawyers": [
    {
      "id": ​1002479,
      "firstname": "Aaron",
      "lastname": "Kiviat",
      "middlename": "S",
      "suffix": null,
      "aliases": [ ],
      "avvo_pro": true,
      "avvo_rating": ​10.0,
      "client_review_count": ​25,
      "client_review_score": ​5.0,
      "headshot_url": "http://placekitten.com/400/400",
      "licensed_since": ​2004,
      "bio": "Lorem ipsum dolores sut amet.",
      "lawyer_specialties": [
        {
          "name": "DUI & DWI",
          "percent": ​25
        },
      ],
      "browse_links": [
        {
          "type": "profile",
          "url": "http://www.avvo.com/attorneys/28895.html"
        },
      ]
    },
  ]
  "meta":{
    "status": ​200,
    "current_page": ​1,
    "per_page": ​10,
    "total_pages": ​227995,
    "total_entries": ​2279945
  }
}

```

### Fields

Field               | Description
--------------------|-------
id                  | Id of the lawyer. This is the primary record key
firstname           | The lawyer's first name
middlename          | The lawyer's middle name
lastname            | The lawyer's last name 
suffix              | Name suffix, e.g. Esq.
aliases             | Other names the lawyers have listed, e.g. Bubba
avvo_pro            | Whether the lawyer is an Avvo Pro
avvo_rating         | The lawyer's Avvo rating
client_review_count | Number of client reviews
client_review_score | The average rating based on client reviews
headshot_url        | The URL to the lawyer's headshot image
licensed_since      | The year in which the lawyer was licensed
bio                 | The lawyer's bio. <aside class="notice">This may be formatted in HTML<aside/>
lawyer_specialties  | The lawyer's specialties. Array of `{"name": "", "percent":""}` JSON blobs
browse_links        | Lawyer links. Can be of type "profile" and "contact". Array of `{"type":"", "url":""}` JSON blobs


## Index [GET]

Look up multiple lawyers by id

### URL

`https://api.avvo.com/api/4/lawyers.json`

### Params

Param     | Value
----------|------
id        | Primary key of the layer

Array of IDs, in the standard Rails format:

`https://api.avvo.com/api/4/lawyers.json?id[]=1&id[]=2`


## Show [GET]

Look up a single lawyer.

### URL

`https://api.avvo.com/api/4/lawyers/:id.json`

Param     | Value
----------|------
id        | Primary key of the lawyer

## Search [GET]

Natural text search for lawyers in location by name or specialty

### URL

`https://api.avvo.com/api/4/lawyers/search.json`

### Params

All of the params are optional

Param               | Description                                               | Values
--------------------|-----------------------------------------------------------|--------
q                   | Query string                                              | Plain English query string, e.g. "DUI" or "Mark Britton"
loc                 | Location string. Can be replaced with lat long values.    | Plain English location string,  e.g. "Seattle, wa"
lat                 | Latitude value                                            | Floating point number
long                | Longitude value                                           | Floating point number
radius              | Search radius. Works for both lat long and `loc` searches | Integer
has_reviews         | Filters lawyers who have reviews                          | true/false
avvo_rating         | Sort by Avvo rating                                       | `not required`
client_rating       | Sort by average value of client ratings                   | `not required`
number_of_reviews   | Sort by number of client reviews                          | `not required`
per_page            | number of lawyers per page                                | `not required`
page                | page number for query                                     | `not required`
