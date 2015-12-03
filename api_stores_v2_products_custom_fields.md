## Custom fields associated with a product.

|||
|---|---|
| **Manages** |
| **OAuth Scopes** | `store_v2_products`
||`store_v2_products_read_only`


## Operations

*   [List Custom Fields](#list-custom-fields)
*   [Get a Custom Field](#get-a-custom-field)
*   [Get a Count of Custom Fields](#get-a-count-of-custom-fields)
*   [Create a Custom Field](#create-a-custom-field)
*   [Update a Custom Field](#update-a-custom-field)
*   [Delete a Custom Field](#delete-a-custom-field)
*   [Delete Multiple Custom Fields](#delete-multiple-custom-fields)

## List Custom Fields

Gets custom fields associated with a product.

*   [OAuth](#list-custom-fields-oauth)
>`GET /stores/{store_hash}/v2/products/{product_id}/custom_fields`</div>
*   [Basic Auth](#list-custom-fields-basic)
>`GET /api/v2/products/{product_id}/custom_fields`</div>


### Pagination

Parameters can be added to the URL query string to paginate the collection. The maximum limit is 250\. If a limit isn’t provided, up to 50 custom_fields are returned by default.

| Parameter | Type | Example |
| --- | --- | --- |
| `Page` | int | `/api/v2/products/{product_id}/custom_fields?page={number}` |
| `Limit` | int | `/api/v2/products/{product_id}/custom_fields?limit={count}` |

### Response

Example JSON returned in the response:

```
[
  {
    "id": 1,
    "product_id": 30,
    "name": "Toy manufactured in",
    "text": "USA"
  },
  {
    "id": 2,
    "product_id": 45,
    "name": "Release Date",
    "text": "2013-12-25"
  }
]
```

## Get a Custom Field

Gets a custom field associated with a product.

*   [OAuth](#get-a-custom-field-oauth)
>`GET /stores/{store_hash}/v2/products/{product_id}/custom_fields/{id}`</div>
*   [Basic Auth](#get-a-custom-field-basic)
>`GET /api/v2/products/{product_id}/custom_fields/{id}`</div>

### Response

Example JSON returned in the response:

```
{
  "id": 2,
  "product_id": 30,
  "name": "Toy manufactured in",
  "text": "USA"
}
```

## Get a Count of Custom Fields

Gets a count of the number of custom fields in the store.

*   [OAuth](#get-a-count-of-custom-fields-oauth)
>`GET /stores/{store_hash}/v2/products/custom_fields/count`</div>
*   [Basic Auth](#get-a-count-of-custom-fields-basic)
>`GET /api/v2/products/custom_fields/count`</div>

### Response

Example JSON returned in the response:

```
{
  "count": 0
}
```

## Create a Custom Field

Creates a new custom field associated with a product


*   [OAuth](#create-a-custom-field-oauth)
>`POST /stores/{store_hash}/v2/products/{product_id}/custom_fields`</div>
*   [Basic Auth](#create-a-custom-field-basic)
>`POST /api/v2/products/{product_id}/custom_fields`</div>

### Read-only Properties

The following properties of the custom field are read-only. If one or more of these properties are included in the request, it will be rejected.

*   `product_id`

### Requirements

The following properties of the custom field are required. The request won’t be fulfilled unless these properties are valid.

*   `name`
*   `text`

### Request

Example request object:

```
{
  "name": "Release Date",
  "text": "2013-12-25"
}
```

### Response

Example JSON returned in the response:

```
{
  "id": 5,
  "product_id": 45,
  "name": "Release Date",
  "text": "2013-12-25"
}
```

## Update a Custom Field

Updates an existing custom field associated with a product.

*   [OAuth](#update-a-custom-field-oauth)
>`PUT /stores/{store_hash}/v2/products/{product_id}/custom_fields/{id}`</div>
*   [Basic Auth](#update-a-custom-field-basic)
>`PUT /api/v2/products/{product_id}/custom_fields/{id}`</div>

### Read-only Properties

The following properties of the custom field are read-only. If one or more of these properties are included in the request, it will be rejected.

*   `product_id`

### Requirements

The following properties of the custom field are required. The request won’t be fulfilled unless these properties are valid.

*   `name`
*   `text`

### Request

Example request object:

```
{
  "name": "Release Date",
  "text": "2013-12-31"
}
```

### Response

Example JSON returned in the response:

```
{
  "id": 5,
  "product_id": 45,
  "name": "Release Date",
  "text": "2013-12-31"
}
```

## Delete a Custom Field

Deletes a custom field associated with a product.

*   [OAuth](#delete-a-custom-field-oauth)
>`DELETE /stores/{store_hash}/v2/products/{product_id}/custom_fields/{id}`</div>
*   [Basic Auth](#delete-a-custom-field-basic)
>`DELETE /api/v2/products/{product_id}/custom_fields/{id}`</div>

## Delete Multiple Custom Fields

Deletes multiple custom fields associated with a product.

*   [OAuth](#delete-multiple-custom-fields-oauth)
>`DELETE /stores/{store_hash}/v2/products/{product_id}/custom_fields`</div>
*   [Basic Auth](#delete-multiple-custom-fields-basic)
>`DELETE /api/v2/products/{product_id}/custom_fields`</div>

### Pagination

Parameters can be added to the URL query string to paginate the collection. The maximum limit is 250\. If a limit isn’t provided, up to 50 custom_fields are returned by default.

| Parameter | Type | Example |
| --- | --- | --- |
| `Page` | int | `/api/v2/products/{product_id}/custom_fields?page={number}` |
| `Limit` | int | `/api/v2/products/{product_id}/custom_fields?limit={count}` |
