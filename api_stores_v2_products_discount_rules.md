## Bulk pricing rules applied to a product.

|||
|---|---|
| Manages |
| OAuth Scopes | `store_v2_products`
||`store_v2_products_read_only`

</div>

</div>

## Operations

*   [List Bulk Pricing Rules](#list-bulk-pricing-rules)
*   [Get a Product Bulk Pricing Rule](#get-a-product-bulk-pricing-rule)
*   [Get a Count of Bulk Pricing Rules](#get-a-count-of-bulk-pricing-rules)
*   [Create a Product Bulk Pricing Rule](#create-a-product-bulk-pricing-rule)
*   [Update a Product Bulk Pricing Rule](#update-a-product-bulk-pricing-rule)
*   [Delete a Product Bulk Pricing Rule](#delete-a-product-bulk-pricing-rule)
*   [Delete Multiple Product Bulk Pricing Rules](#delete-multiple-product-bulk-pricing-rules)

## List Bulk Pricing Rules

Gets the collection of product bulk pricing rules.

*   [OAuth](#list-bulk-pricing-rules-oauth)
>`GET /stores/{store_hash}/v2/products/{product_id}/discount_rules`</div>
*   [Basic Auth](#list-bulk-pricing-rules-basic)
>`GET /api/v2/products/{product_id}/discount_rules`</div>

### Pagination

Parameters can be added to the URL query string to paginate the collection. The maximum limit is 250\. If a limit isn’t provided, up to 50 bulk_pricing_rules are returned by default.

| Parameter | Type | Example |
| --- | --- | --- |
| `page` | int | `/api/v2/products/{product_id}/discount_rules?page={number}` |
| `limit` | int | `/api/v2/products/{product_id}/discount_rules?limit={count}` |

### Response

Example JSON returned in the response:

```
[
  {
    "id": "1",
    "product_id": 30,
    "min": 100,
    "max": 500,
    "type": "price",
    "type_value": 2
  }
]
```

## Get a Product Bulk Pricing Rule

Gets a product bulk pricing rule.

*   [OAuth](#get-a-product-bulk-pricing-rule-oauth)
>`GET /stores/{store_hash}/v2/products/{product_id}/discount_rules/{id}`</div>
*   [Basic Auth](#get-a-product-bulk-pricing-rule-basic)
>`GET /api/v2/products/{product_id}/discount_rules/{id}`</div>

### Response

Example JSON returned in the response:

```
{
  "id": "1",
  "product_id": 30,
  "min": 100,
  "max": 500,
  "type": "price",
  "type_value": 2
}
```

## Get a Count of Bulk Pricing Rules

Gets a count of the number of bulk pricing rules in the store.

*   [OAuth](#get-a-count-of-bulk-pricing-rules-oauth)
>`GET /stores/{store_hash}/v2/products/discount_rules/count`</div>
*   [Basic Auth](#get-a-count-of-bulk-pricing-rules-basic)
>`GET /api/v2/products/discount_rules/count`</div>

### Response

Example JSON returned in the response:

```
{
  "count": 9
}
```

## Create a Product Bulk Pricing Rule

Creates a new product bulk pricing rule.

*   [OAuth](#create-a-product-bulk-pricing-rule-oauth)
>`POST /stores/{store_hash}/v2/products/{product_id}/discount_rules`</div>
*   [Basic Auth](#create-a-product-bulk-pricing-rule-basic)
>`POST /api/v2/products/{product_id}/discount_rules`</div>

### Read-only Properties

The following properties of the discount rule are read-only. If one or more of these properties are included in the request, it will be rejected.

*   `product_id`

### Requirements

The following properties of the discount rule are required. The request won’t be fulfilled unless these properties are valid.

*   `type`
*   `type_value`

### Notes

To specify that a `min` or `max` value is unbounded, these properties must be explicitly set with a value of `0`. If neither `min` nor `max` properties are included in the request, the existing value will remain unchanged.

The range of the `min` and `max` values must not overlap an existing rule associated with the same product.

### Request

Example request object:

```
{
  "min": 100,
  "max": 500,
  "type": "price",
  "type_value": 2
}
```

### Response

Example JSON returned in the response:

```
{
  "id": "1",
  "product_id": 30,
  "min": 100,
  "max": 500,
  "type": "price",
  "type_value": 2
}
```

## Update a Product Bulk Pricing Rule

Updates an existing product bulk pricing rule.

*   [OAuth](#update-a-product-bulk-pricing-rule-oauth)
>`PUT /stores/{store_hash}/v2/products/{product_id}/discount_rules/{id}`</div>
*   [Basic Auth](#update-a-product-bulk-pricing-rule-basic)
>`PUT /api/v2/products/{product_id}/discount_rules/{id}`</div>

### Read-only Properties

The following properties of the discount rule are read-only. If one or more of these properties are included in the request, it will be rejected.

*   `product_id`

### Requirements

The following properties of the discount rule are required. The request won’t be fulfilled unless these properties are valid.

*   `type`
*   `type_value`

### Notes

To specify that a `min` or `max` value is unbounded, these properties must be explicitly set with a value of `0`. If neither `min` nor `max` properties are included in the request, the existing value will remain unchanged.

The range of the `min` and `max` values must not overlap an existing rule associated with the same product.

### Request

Example request object:

```
{
  "min": 200,
  "max": 300,
  "type": "fixed",
  "type_value": 10
}
```

### Response

Example JSON returned in the response:

```
{
  "id": "1",
  "product_id": 30,
  "min": 200,
  "max": 300,
  "type": "fixed",
  "type_value": 10
}
```

## Delete a Product Bulk Pricing Rule

Deletes a product bulk pricing rule.

*   [OAuth](#delete-a-product-bulk-pricing-rule-oauth)
>`DELETE /stores/{store_hash}/v2/products/{product_id}/discount_rules/{id}`</div>
*   [Basic Auth](#delete-a-product-bulk-pricing-rule-basic)
>`DELETE /api/v2/products/{product_id}/discount_rules/{id}`</div>

## Delete Multiple Product Bulk Pricing Rules

Deletes bulk pricing rules associated with a product.

*   [OAuth](#delete-multiple-product-bulk-pricing-rules-oauth)
>`DELETE /stores/{store_hash}/v2/products/{product_id}/discount_rules`</div>
*   [Basic Auth](#delete-multiple-product-bulk-pricing-rules-basic)
>`DELETE /api/v2/products/{product_id}/discount_rules`</div>

### Pagination

Parameters can be added to the URL query string to paginate the collection. The maximum limit is 250\. If a limit isn’t provided, up to 50 bulk_pricing_rules are returned by default.

| Parameter | Type | Example |
| --- | --- | --- |
| `Page` | int | `/api/v2/products/{product_id}/discount_rules?page={number}` |
| `Limit` | int | `/api/v2/products/{product_id}/discount_rules?limit={count}` |
