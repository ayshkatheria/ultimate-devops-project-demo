# Checkout Service

This service provides checkout services for the application.

## Local Build

To build the service binary, run:

```sh
go build -o /go/bin/checkout/
```

## Docker Command to run 

```sh
docker run -d -e SHIPPING_ADDR="abcd" \
           -e PRODUCT_CATALOG_ADDR="abd" \
           -e CART_ADDR="cart_dress" \
           -e CURRENCY_ADDR="currency_service_address" \
           -e EMAIL_ADDR="email_service_address" \
           -e PAYMENT_ADDR="payment_service_address" \
           -p 8088:8088 aysh/checkout:v2

```

## Docker Build

From the root directory, run:

```sh
docker compose build checkout
```

## Regenerate protos

To build the protos, run from the root directory:

```sh
make docker-generate-protobuf
```

## Bump dependencies

To bump all dependencies run:

```sh
go get -u -t ./...
go mod tidy
```
