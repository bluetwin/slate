# Reviews

Lawyer reviews. These are the reviews that are visible for lawyers on the website. 

> Example response

```json
{
  "reviews": [
    {
      "lawyer_id": ​28995,
      "title": "Great GC when at Expedia",
      "body": "I worked with Mark for 4 years while we were at Expedia together. He was GC for most of this time. I found Mark to be extremely sharp, able to integrate business and legal thinking in such a way as to deliver answers to problems that appropriately balanced risks and opportunities, something that I think is vital in a GC yet can be hard to find."
    }
  ],
  "meta": 
  {
    "status": ​200,
    "current_page": ​1,
    "per_page": ​10,
    "total_pages": ​1,
    "total_entries": ​1
  }
}
```

### Fields

Field     | Description
----------|------------
lawyer_id | The lawyer's id
rating    | The client's rating of the lawyer (0 - 5)
title     | The title of the review
body      | The body text of the review


## Index [GET]

Get reviews for a specific lawyer

### URL

`https://api.avvo.com/api/4/reviews.json`

### Params

Param     | Value
----------|------
lawyer_id | primary key of lawyer whose reviews you need to get

Array of `lawyer_id`s, in the standard Rails format:

`https://api.avvo.com/api/4/reviews.json?lawyer_id[]=1&lawyer_id[]=2`