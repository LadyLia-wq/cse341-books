# Books API Specification – Version 1

# Purpose
Create a basic web service that returns book data stored in MongoDB.

# Data Model

Book fields:
- `id`: string
- `author`: string
- `title`: string
- `publicationDate`: string

# Endpoints

# 1. GET /books
- Returns all books.
- Response status: 200 on success.

# 2. GET /books/:id
- Returns one book matching the provided ID.
- Response status: 200 on success.
- If no matching book is found, return 404.

# Initial Assumptions
- Data is stored in a MongoDB collection named `books`.
- The API returns JSON responses.







# Books API Specification – Version 2

# Purpose
Build a read-only Books API using Express.js and MongoDB.

# Database
- Database: `cse341-books-db`
- Collection: `books`

# Data Model

Each book must contain:

- `id`: string (required)
- `author`: string (required)
- `title`: string (required)
- `publicationDate`: string in ISO 8601 date format (e.g. `2021-08-17`) (required)

# Endpoints

# 1. GET /books

Description:
Return all books stored in the MongoDB books collection.

Success:
- HTTP 200
- Return a JSON array of book objects.

Example response:

[
  {
    "id": "b1",
    "author": "Maya Rivera",
    "title": "Patterns of Light",
    "publicationDate": "2021-08-17"
  }
]

Error:
- HTTP 500

{
  "message": "Internal server error"
}

# 2. GET /books/:id

Description:
Return one book matching the supplied custom ID.

Success:
- HTTP 200
- Return one JSON book object.

Example response:

{
  "id": "b1",
  "author": "Maya Rivera",
  "title": "Patterns of Light",
  "publicationDate": "2021-08-17"
}

Not found:
- HTTP 404

{
  "message": "Book not found"
}

Server error:
- HTTP 500

{
  "message": "Internal server error"
}

# Error Handling
- Do not expose database error details or stack traces to clients.
- Return safe, understandable JSON error messages.
- Use appropriate HTTP status codes.

# Implementation Notes
- Use the MongoDB collection named `books`.
- Seed the collection with at least three book documents.
- Store MongoDB connection details in environment variables.
- Connect to MongoDB before the Express server begins listening.

# Out of Scope
- POST routes
- PUT routes
- DELETE routes
- Authentication and authorization