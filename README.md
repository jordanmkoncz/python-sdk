# Python SDK

[Website] (http://molt.in)

License: MIT

Version: 1

## Description

Python SDK for the Moltin eCommerce API

## Installation

    $ pip install moltin

## Usage

Initialise the Moltin object with your `client_id` and `client_secret`, and optionally a specific API version (e.g. `v1`).

```python
    from moltin.moltin import *
    
    m = Moltin("YOUR_CLIENT_ID", "YOUR_CLIENT_SECRET"[, version="v1"])
```    

### Authentication

To Authenticate, call the authenticate method.

```python
    m.authenticate()
```
    
If authenticating with a username/password:

```python
    m.authenticate(username="your_username", password="your_password")
    
    refresh_token = m.refresh_token  # used for re-authenticating without user/pass
```

If authenticating with a refresh_token:

```python
    m.authenticate(refresh_token="token")
```

### Making API Calls

The SDK offers a way to easily interact with most of the API endpoints.

Creating a product example:

```python
    products = Product(m)  #  pass in the authenticated Moltin object
    
    params = {
        "sku": "123456789",
        "title": "My first product",
        "slug": "my-first-product",
        "price": 9.99,
        "status": 1,
        "category": 2,
        "stock_level": 15,
        "stock_status": 6,
        "description": "This is my first product on Moltin",
        "requires_shipping": 0
    }
    
    products.create(params)
```

For more examples, see the full API docs.
