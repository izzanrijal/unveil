# Checkout Links API

## Create Checkout Link

Creates a payment link that can be shared with customers to complete a purchase.

**Endpoint:** `POST /v1/checkout/links`

**Authentication Required:** Yes

### Request Body

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `product_id` | string | Yes | The ID of the product to create a link for |
| `success_url` | string | Yes | The URL to redirect to after a successful purchase |
| `cancel_url` | string | Yes | The URL to redirect to if the customer cancels |
| `allow_promotion_codes` | boolean | No | Whether to allow promotion codes to be used with this link |
| `billing_address_collection` | string | No | Whether to collect billing address. Can be `auto` or `required` |
| `client_reference_id` | string | No | A unique string to reference this checkout link |
| `customer_creation` | string | No | Whether to create a new customer or use an existing one. Can be `always` or `if_required` |
| `mode` | string | No | The mode of the checkout link. Can be `payment`, `setup`, or `subscription` |

### Response

```json
{
  "id": "cl_123abc",
  "object": "checkout.link",
  "active": true,
  "allow_promotion_codes": false,
  "amount_subtotal": 1000,
  "amount_total": 1000,
  "cancel_url": "https://your-website.com/cancel",
  "client_reference_id": "order_123",
  "created": 1610000000,
  "currency": "usd",
  "customer": null,
  "livemode": false,
  "metadata": {},
  "mode": "payment",
  "payment_intent": "pi_123abc",
  "payment_link": "https://checkout.polar.sh/pay/cl_123abc",
  "payment_method_types": ["card"],
  "product": {
    "id": "prod_123abc",
    "name": "Premium Plan",
    "description": "Access to all premium features"
  },
  "status": "open",
  "success_url": "https://your-website.com/success?session_id={CHECKOUT_SESSION_ID}",
  "url": "https://checkout.polar.sh/pay/cl_123abc"
}
```

### Example Request

```bash
curl -X POST https://api.polar.sh/v1/checkout/links \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "product_id": "prod_123abc",
    "success_url": "https://your-website.com/success?session_id={CHECKOUT_SESSION_ID}",
    "cancel_url": "https://your-website.com/cancel"
  }'
```

## Retrieve Checkout Link

Retrieves the details of an existing checkout link.

**Endpoint:** `GET /v1/checkout/links/{link_id}`

**Authentication Required:** Yes

### Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `link_id` | string | Yes | The ID of the checkout link to retrieve |

### Response

Returns the same object structure as the Create Checkout Link response.

### Example Request

```bash
curl -X GET https://api.polar.sh/v1/checkout/links/cl_123abc \
  -H "Authorization: Bearer YOUR_API_KEY"
```

## List Checkout Links

Returns a list of checkout links.

**Endpoint:** `GET /v1/checkout/links`

**Authentication Required:** Yes

### Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `active` | boolean | No | Only return active or inactive links |
| `limit` | integer | No | A limit on the number of objects to be returned |
| `starting_after` | string | No | A cursor for use in pagination |
| `ending_before` | string | No | A cursor for use in pagination |

### Response

```json
{
  "object": "list",
  "data": [
    {
      "id": "cl_123abc",
      "object": "checkout.link",
      "active": true,
      "amount_subtotal": 1000,
      "amount_total": 1000,
      "url": "https://checkout.polar.sh/pay/cl_123abc",
      "created": 1610000000,
      "currency": "usd",
      "livemode": false,
      "metadata": {}
    }
  ],
  "has_more": false,
  "url": "/v1/checkout/links"
}
```

### Example Request

```bash
curl -X GET "https://api.polar.sh/v1/checkout/links?active=true&limit=10" \
  -H "Authorization: Bearer YOUR_API_KEY"
```
