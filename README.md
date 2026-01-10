# Books-API-Testing

The API is available at `https://simple-books-api.click`

## Endpoints ##

### Status ###

GET `/status`

Returns the status of the API.

### List of books ###

GET `/books`

Returns a list of books.

Optional query parameters:

- type: fiction or non-fiction
- limit: a number between 1 and 20.


### Get a single book ###

GET `/books/:bookId`

Retrieve detailed information about a book.


### Submit an order ###

POST `/orders`

The request body needs to be in JSON format and include the following properties:

 - `bookId` - Integer - Required
 - `customerName` - String - Required

The response body will contain the order Id.

### Get all orders ###

GET `/orders`

### Get an order ###

GET `/orders/:orderId`

### Update an order ###

PATCH `/orders/:orderId`

Update an existing order. Requires authentication.

The request body needs to be in JSON format and allow for updating the following properties:

 - `customerName` - String

{
  "customerName": "John"
}
```

### Delete an order ###

DELETE `/orders/:orderId`

Delete an existing order. Requires authentication.

The request body needs to be empty.

## API Authentication ##

To submit or view an order, need to register an API client.

POST `/api-clients/`

The request body needs to be in JSON format and include the following properties:

 - `clientName` - String
 - `clientEmail` - String

 Example

 ```
 {
    "clientName": "valentin",
    "clientEmail": "valentin@example.com"
}
 ```

**Possible errors**

Status code 409 - "API client already registered." Try changing the values for `clientEmail` and `clientName` to something else.
