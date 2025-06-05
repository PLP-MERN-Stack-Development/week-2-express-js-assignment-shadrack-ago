[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=19701833&assignment_repo_type=AssignmentRepo)
# Express.js RESTful API Assignment

This assignment focuses on building a RESTful API using Express.js, implementing proper routing, middleware, and error handling.

## Assignment Overview

You will:
1. Set up an Express.js server
2. Create RESTful API routes for a product resource
3. Implement custom middleware for logging, authentication, and validation
4. Add comprehensive error handling
5. Develop advanced features like filtering, pagination, and search

## Getting Started

1. Accept the GitHub Classroom assignment invitation
2. Clone your personal repository that was created by GitHub Classroom
3. Install dependencies:
   ```
   npm install
   ```
4. Run the server:
   ```
   npm start
   ```

## Files Included

- `Week2-Assignment.md`: Detailed assignment instructions
- `server.js`: Starter Express.js server file
- `.env.example`: Example environment variables file

## Requirements

- Node.js (v18 or higher)
- npm or yarn
- Postman, Insomnia, or curl for API testing

## API Endpoints

The API will have the following endpoints:

- `GET /api/products`: Get all products
- `GET /api/products/:id`: Get a specific product
- `POST /api/products`: Create a new product
- `PUT /api/products/:id`: Update a product
- `DELETE /api/products/:id`: Delete a product

## Submission

Your work will be automatically submitted when you push to your GitHub Classroom repository. Make sure to:

1. Complete all the required API endpoints
2. Implement the middleware and error handling
3. Document your API in the README.md
4. Include examples of requests and responses

## Resources

- [Express.js Documentation](https://expressjs.com/)
- [RESTful API Design Best Practices](https://restfulapi.net/)
- [HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) 


My API documentation
 Product API Documentation
Base URL: http://localhost:3000/api

🛑 Authentication
Requires x-api-key: your-secret-key in headers for protected routes (POST/PUT/DELETE).

📦 Products Endpoints
1. Get All Products
GET /products
Query Params:

category (optional): Filter by category (e.g., electronics)

page (optional): Pagination page number

limit (optional): Items per page (default: 10)

Response:

json
{
  "total": 3,
  "page": 1,
  "limit": 10,
  "data": [
    {
      "id": "1",
      "name": "Laptop",
      "description": "High-performance laptop",
      "price": 1200,
      "category": "electronics",
      "inStock": true
    }
  ]
}
2. Get Single Product
GET /products/:id
Response (Success):

json
{
  "id": "1",
  "name": "Laptop",
  ...
}
Response (Error):

json
{ "error": "Product not found" }
3. Create Product
POST /products
Headers:

Content-Type: application/json

x-api-key: your-secret-key

Request Body:

json
{
  "name": "Smartphone",
  "description": "Latest model",
  "price": 800,
  "category": "electronics",
  "inStock": true
}
Response (Success):

json
{
  "id": "4",
  "name": "Smartphone",
  ...
}
4. Update Product
PUT /products/:id
Headers: Same as POST
Request Body: Partial updates allowed (e.g., just { "price": 750 })
Response: Updated product JSON.

5. Delete Product
DELETE /products/:id
Response: HTTP 204 (No Content) on success.

⚙️ Error Responses
400 Bad Request: Missing/invalid fields

401 Unauthorized: Invalid API key

404 Not Found: Product ID not found

500 Server Error: Internal server error

📌 Example Requests:

bash
curl -X GET http://localhost:3000/api/products
curl -X POST -H "x-api-key: your-secret-key" -d '{"name":"Keyboard"}' http://localhost:3000/api/products
For post request you must use the auth keys