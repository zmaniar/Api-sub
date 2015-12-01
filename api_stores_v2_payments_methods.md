## Enabled payment methods.

|||
|---|---|
| Manages |
| OAuth Scopes | `store_v2_information`
||`store_v2_information_read_only`


</div>

</div>

## Operations

*   [List Payment Methods](#list-payment-methods)

## List Payment Methods

Gets the list of enabled payment methods. (Default sorting is by payment method, alphabetically from A to Z.)

<div class="bui-tabs">

*   [OAuth](#list-payment-methods-oauth)
*   [Basic Auth](#list-payment-methods-basic)

<div class="bui-tab-panel is-active" id="list-payment-methods-oauth">`GET /stores/{store_hash}/v2/payments/methods`</div>

<div class="bui-tab-panel" id="list-payment-methods-basic">`GET /api/v2/payments/methods`</div>

</div>

### Filters

Filter parameters can be added to the URL query string to select specific payment_methods in the collection.

| Parameter | Type | Example |
| --- | --- | --- |

### Pagination

Parameters can be added to the URL query string to paginate the collection. The maximum limit is 250\. If a limit isn’t provided, up to 50 payment_methods are returned by default.

| Parameter | Type | Example |
| --- | --- | --- |
| `Page` | int | `/api/v2/payments/methods?page={number}` |
| `Limit` | int | `/api/v2/payments/methods?limit={count}` |

### Response

Example JSON returned in the response:

<pre class="bui-message bui-message-info">[
  {
    "code": "bankdeposit",
    "name": "Bank Deposit",
    "test_mode": false
  },
  {
    "code": "cod",
    "name": "Cash on Delivery",
    "test_mode": false
  },
  {
    "code": "paypalexpress",
    "name": "PayPal Express Checkout",
    "test_mode": false
  },
  {
    "code": "stripe",
    "name": "Stripe",
    "test_mode": false
  }
]</pre>
