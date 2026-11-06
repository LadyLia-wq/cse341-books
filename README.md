# CSE 341 – Books Web Service

A RESTful Books API built with Node.js, Express.js, and MongoDB. The application follows the Model-View-Controller (MVC) architecture.

## Live Deployment

**Base URL:** https://cse341-books-ftfn.onrender.com

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Checks if the server is running |
| GET | `/books` | Retrieves all books |
| GET | `/books/:id` | Retrieves a book by its custom ID |

## Example Requests

- [Get all books](https://cse341-books-ftfn.onrender.com/books)
- [Get book b1](https://cse341-books-ftfn.onrender.com/books/b1)
- [Test missing book](https://cse341-books-ftfn.onrender.com/books/does-not-exist)

## Response Status Codes

- `200 OK` – Request successful.
- `404 Not Found` – Requested book does not exist.
- `500 Internal Server Error` – An unexpected server error occurred.

## Technologies Used

- Node.js
- Express.js
- MongoDB Atlas
- JavaScript (ES Modules)
- ESLint
- Render

## Environment Variables

Configure the following variables in your local `.env` file:

- `MONGODB_URI`
- `MONGODB_DB_NAME`
- `PORT`

For Render deployment, configure `MONGODB_URI` and `MONGODB_DB_NAME` in the service's Environment settings. Render supplies `PORT` automatically.

**Note:** Never commit your `.env` file or expose database credentials.

## API Specification

See [BOOKS-API-SPECIFICATION.md](./BOOKS-API-SPECIFICATION.md) for the detailed API specification.

## Deployment Verification

The deployed application was tested successfully:

- `GET /` returned HTTP 200.
- `GET /books` returned all three books.
- `GET /books/b1` returned the requested book.
- `GET /books/does-not-exist` returned the expected 404 JSON response.
- Server error handling was reviewed to confirm safe JSON responses.