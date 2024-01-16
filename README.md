The TcFootwear E-Commerce Backend API is built using Spring Boot and facilitates the core functionalities of our e-commerce platform. It includes features for product management and order processing.

Functional Requirements

Product Management
1.1 Create a Product
Endpoint: > POST /api/products
Request Payload: { "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100 }
Response Payload: { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100 }
Description: Creates a new product with the given name, description, price, and stock quantity. Error Handling: Returns a 400 Bad Request error if the request payload is invalid.
Database Operation: Inserts a new product into the database.

1.2 Get All Products
Endpoint: GET /api/products
Response Payload: [ { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100 }, { "id": 2, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100 } ]

Description: Returns a list of all products. 
Error Handling: Returns a 500 Internal Server Error error if the database operation fails.
Database Operation: Retrieves all products from the database.

1.3 Get a Product
Endpoint: GET /api/products/{id} 
Response Payload: { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100 } 
Description: Returns the product with the given ID. Error Handling: Returns a 404 Not Found error if the product with the given ID does not exist.
Database Operation: Retrieves the product with the given ID from the database.

1.4 Update a Product
Endpoint: PUT /api/products/{id} 
Request Payload: { "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100 }
Response Payload: { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100 }

Description: Updates the product with the given ID.
Error Handling: Returns a 400 Bad Request error if the request payload is invalid. Returns a 404 Not Found error if the product with the given ID does not exist. Database Operation: Updates the product with the given ID in the database.

1.5 Delete a Product
Endpoint: DELETE /api/products/{id} Description: Deletes the product with the given ID.
Error Handling: Returns a 404 Not Found error if the product with the given ID does not exist.
Database Operation: Deletes the product with the given ID from the database.

Order Management 2.1 Create an Order Endpoint: POST /api/orders
Request Payload:

{ "products": [ { "id": 1, "quantity": 2 }, { "id": 2, "quantity": 1 } ] } Response Payload:

{ "id": 1, "products": [ { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 2 },
{ "id": 2, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 1 } ], "totalPrice": 89.97 } 
Description: Creates a new order with the given products.

Error Handling: Returns a 400 Bad Request error if the request payload is invalid. Returns a 404 Not Found error if any of the products do not exist. Returns a 409 Conflict error if any of the products do not have enough stock.

Database Operation: Inserts a new order into the database.

2.2 Get All Orders
Endpoint: GET /api/orders
Response Payload: [ { "id": 1, "products": [ { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 2 }, { "id": 2, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 1 } ], "totalPrice": 89.97 },
{ "id": 2, "products": [ { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 2 }, { "id": 2, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 1 } ], "totalPrice": 89.97 } ]
Description: Returns a list of all orders. 
Error Handling: Returns a 500 Internal Server Error error if the database operation fails. 
Database Operation: Retrieves all orders from the database.

2.3 Get an Order Endpoint: GET /api/orders/{id}

Response Payload:

{ "id": 1, "products": [ { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 2 }, { "id": 2, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 1 } ], "totalPrice": 89.97 } 
Description: Returns the order with the given ID.

Error Handling: Returns a 404 Not Found error if the order with the given ID does not exist.

Database Operation: Retrieves the order with the given ID from the database.

2.4 Update an Order
Endpoint: PUT /api/orders/{id} Request Payload: { "products": [ { "id": 1, "quantity": 2 }, { "id": 2, "quantity": 1 } ] }
Response Payload: { "id": 1, "products": [ { "id": 1, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 2 }, { "id": 2, "name": "Product Name", "description": "Product Description", "price": 29.99, "stockQuantity": 100, "quantity": 1 } ], "totalPrice": 89.97 }

Description: Updates the order with the given ID.
Error Handling: Returns a 400 Bad Request error if the request payload is invalid. Returns a 404 Not Found error if the order with the given ID does not exist. Returns a 409 Conflict error if any of the products do not have enough stock.
Database Operation: Updates the order with the given ID in the database.

2.5 Delete an Order Endpoint: DELETE /api/orders/{id}

Description: Deletes the order with the given ID.

Error Handling: Returns a 404 Not Found error if the order with the given ID does not exist.

Database Operation: Deletes the order with the given ID from the database.

Technical Requirements The API must be built using Spring Boot. The API must be backed by a MySQL database. The API must be documented using Swagger.
