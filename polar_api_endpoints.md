# Polar.sh API Endpoints Reference

## Core API

### Checkout
- `POST /api-reference/checkouts/create-session` - Create Checkout Session
- `GET /api-reference/checkouts/get-session` - Get Checkout Session
- `GET /api-reference/checkouts/list-sessions` - List Checkout Sessions
- `PATCH /api-reference/checkouts/update-session` - Update Checkout Session
- `GET /api-reference/checkouts/get-session-from-client` - Get Checkout Session from Client
- `PATCH /api-reference/checkouts/update-session-from-client` - Update Checkout Session from Client
- `POST /api-reference/checkouts/confirm-session-from-client` - Confirm Checkout Session from Client

### Checkout Links
- `POST /api-reference/checkout-links/create` - Create Checkout Link
- `GET /api-reference/checkout-links/get` - Get Checkout Link
- `GET /api-reference/checkout-links/list` - List Checkout Links
- `PATCH /api-reference/checkout-links/update` - Update Checkout Link
- `DELETE /api-reference/checkout-links/delete` - Delete Checkout Link

### Custom Checkout Fields
- `GET /api-reference/custom-checkout-fields/list` - List Custom Checkout Fields
- `POST /api-reference/custom-checkout-fields/create` - Create Custom Checkout Field
- `GET /api-reference/custom-checkout-fields/get` - Get Custom Checkout Field
- `PATCH /api-reference/custom-checkout-fields/update` - Update Custom Checkout Field
- `DELETE /api-reference/custom-checkout-fields/delete` - Delete Custom Checkout Field

### Customers
- `GET /api-reference/customers/list` - List Customers
- `POST /api-reference/customers/create` - Create Customer
- `GET /api-reference/customers/get` - Get Customer
- `PATCH /api-reference/customers/update` - Update Customer
- `DELETE /api-reference/customers/delete` - Delete Customer

### Subscriptions
- `GET /api-reference/subscriptions/list` - List Subscriptions
- `POST /api-reference/subscriptions/create` - Create Subscription
- `GET /api-reference/subscriptions/get` - Get Subscription
- `PATCH /api-reference/subscriptions/update` - Update Subscription
- `DELETE /api-reference/subscriptions/cancel` - Cancel Subscription

### Products
- `GET /api-reference/products/list` - List Products
- `POST /api-reference/products/create` - Create Product
- `GET /api-reference/products/get` - Get Product
- `PATCH /api-reference/products/update` - Update Product
- `DELETE /api-reference/products/delete` - Delete Product

### Orders
- `GET /api-reference/orders/list` - List Orders
- `POST /api-reference/orders/create` - Create Order
- `GET /api-reference/orders/get` - Get Order
- `POST /api-reference/orders/update` - Update Order
- `POST /api-reference/orders/pay` - Pay Order

### Discounts
- `GET /api-reference/discounts/list` - List Discounts
- `POST /api-reference/discounts/create` - Create Discount
- `GET /api-reference/discounts/get` - Get Discount
- `PATCH /api-reference/discounts/update` - Update Discount
- `DELETE /api-reference/discounts/delete` - Delete Discount

### Refunds
- `GET /api-reference/refunds/list` - List Refunds
- `POST /api-reference/refunds/create` - Create Refund
- `GET /api-reference/refunds/get` - Get Refund
- `POST /api-reference/refunds/update` - Update Refund

### Events
- `GET /api-reference/events/list` - List Events
- `GET /api-reference/events/get` - Get Event

### Meters
- `GET /api-reference/meters/list` - List Meters
- `POST /api-reference/meters/create` - Create Meter
- `GET /api-reference/meters/get` - Get Meter
- `PATCH /api-reference/meters/update` - Update Meter
- `DELETE /api-reference/meters/delete` - Delete Meter

### Benefits
- `GET /api-reference/benefits/list` - List Benefits
- `POST /api-reference/benefits/create` - Create Benefit
- `GET /api-reference/benefits/get` - Get Benefit
- `PATCH /api-reference/benefits/update` - Update Benefit
- `DELETE /api-reference/benefits/delete` - Delete Benefit

### Customer Meters
- `GET /api-reference/customer-meters/list` - List Customer Meters
- `POST /api-reference/customer-meters/create` - Create Customer Meter
- `GET /api-reference/customer-meters/get` - Get Customer Meter
- `PATCH /api-reference/customer-meters/update` - Update Customer Meter
- `DELETE /api-reference/customer-meters/delete` - Delete Customer Meter

### License Keys
- `GET /api-reference/license-keys/list` - List License Keys
- `POST /api-reference/license-keys/create` - Create License Key
- `GET /api-reference/license-keys/get` - Get License Key
- `PATCH /api-reference/license-keys/update` - Update License Key
- `DELETE /api-reference/license-keys/delete` - Delete License Key

### Files
- `GET /api-reference/files/list` - List Files
- `POST /api-reference/files/upload` - Upload File
- `GET /api-reference/files/get` - Get File
- `DELETE /api-reference/files/delete` - Delete File

### Organizations
- `GET /api-reference/organizations/list` - List Organizations
- `POST /api-reference/organizations/create` - Create Organization
- `GET /api-reference/organizations/get` - Get Organization
- `PATCH /api-reference/organizations/update` - Update Organization
- `DELETE /api-reference/organizations/delete` - Delete Organization

### Metrics
- `GET /api-reference/metrics` - Get Metrics

## Authentication
- `POST /api-reference/auth/login` - Login
- `POST /api-reference/auth/refresh` - Refresh Token
- `POST /api-reference/auth/logout` - Logout

## Webhooks
- `POST /api-reference/webhooks` - Handle Webhook Events

## Rate Limits
- `GET /api-reference/rate-limits` - View Rate Limits

## Usage

Gunakan endpoint di atas dengan menambahkan base URL `https://api.polar.sh`. Contoh:
```
GET https://api.polar.sh/api-reference/customers/list
Authorization: Bearer YOUR_API_KEY
```

## Authentication

Semua request membutuhkan API Key yang valid di header Authorization:
```
Authorization: Bearer YOUR_API_KEY
```
