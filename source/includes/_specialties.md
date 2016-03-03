# Specialties

Get single, bulk, or search for specialties that Avvo has listed.

> Example response

```json
{
  "specialties": [
    {

      "id": ​56,
      "name": "DUI & DWI",
      "description": "If you are suspected of driving while under the influence of alcohol or drugs, you may be arrested for DUI (driving under the influence). Depending on the state, the specific crime is also called DWI (driving while intoxicated), OUI (operating under the influence), or OWI (operating while intoxicated). A DUI conviction has serious consequences (for example, losing your driving privileges); but an experienced DUI attorney can often get the charges dropped or reduced, or may be able to negotiate lesser penalties depending on your circumstances and your past history."
    }

  ],
  "meta": 
    {
        "status": ​200,
        "current_page": ​1,
        "per_page": ​30,
        "total_pages": ​1,
        "total_entries": ​2
    }
}
```

### Fields

Field       | Description
------------|------------
id          | Primary key
name        | Spcialty name
description | Brief description of the specialty

## Index [GET]

Get multiple specialties

### URL

`https://api.avvo.com/api/4/specialties.json`

### Params

Param     | Value
----------|------
id        | Primary key of the specialty

Array of IDs, in the standard Rails format:

`https://api.avvo.com/api/4/specialties.json?id[]=1&id[]=2`

## Show [GET]

Get single specialty by id

### URL

`https://api.avvo.com/api/4/specialties/:id.json`

### Params

Param     | Value
----------|------
id        | Primary key of the specialty

## Search [GET]

Find a specialty by a natural language string. 

### URL

`https://api.avvo.com/api/4/specialties/search.json`

### Params

Param     | Description   | Values
----------|---------------|-------
q         | Query string  | Plain English query string, e.g. "Dui"