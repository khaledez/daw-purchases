# Dockerised Purchases API

A sample API for Discount Ascii Warehouse shipped with docker

## Install and start the server

- `docker build -t khaledez/daw-purchases-node .`
- `docker run -p 8000:8000 -d khaledez/daw-purchases-node`

Now you can make API requests, eg: `curl -i localhost:8000/api/users/`

Data will be generated automatically

## API Reference

### GET purchases/by_user/:username

- params:
  - username (string)
  - ?limit (int)

- response (json):

```
{
  "purchases": [
    {
      "id": (int),
      "product_id": (int),
      "username": (string),
      "date": (iso8601 string)
    },
    ...
  ]
}
```

### GET purchases/by_product/:product_id

- params:
  - product_id (int)
  - ?limit (int)

- response: same as `GET purchases/by_user/:username`

### POST purchase

- body (json):

```
{
  "username": (string)
  "product_id": (int)
}
```

### GET products/:id

- params:
  - id (int)

- response (json):

```
{
  "id": (int),
  "face": (string),
  "size": (int),
  "price": (int)
}
```

### GET users

- params:
  - ?limit (int)

- response (json):

```
{
  "users": [
    {
      "username": (string),
      "email": (string)
    },
    ...
  ]
}
```

### GET users/:username

- params:
  - username (string)

- response (json):

```
{
  "username": (string),
  "email": (string)
}
```
