# Book Management API

This is a simple book management API built with Node.js using Hapi.js framework. It allows you to perform CRUD operations (Create, Read, Update, Delete) on a collection of books.

## Getting Started

To get started with this project, follow the steps below:

1. Clone this repository to your local machine.
2. Navigate to the project directory.
3. Install dependencies by running `npm install`.
4. Start the server by running `npm start`.

## Endpoints

### Add a Book

- **URL:** `/books`
- **Method:** `POST`
- **Request Body:**
  ```json
  {
    "name": "Name of the Book",
    "year": 2024,
    "author": "Author Name",
    "summary": "Summary of the book",
    "publisher": "Publisher Name",
    "pageCount": 300,
    "readPage": 150,
    "reading": true
  }
  
- **Response:**
  ```json
  {
    "status": "success",
    "message": "Buku berhasil ditambahkan",
    "data": {
      "bookId": "generatedId"
    }
  }
  ```

### Get All Books

- **URL:** `/books`
- **Method:** `GET`
- **Query Parameters:**
  - `name` (optional): Filter books by name.
  - `reading` (optional): Filter books by reading status (0 or 1).
  - `finished` (optional): Filter books by finished status (0 or 1).
- **Response:**
  ```json
  {
    "status": "success",
    "data": {
      "books": [
        {
          "id": "bookId",
          "name": "Name of the Book",
          "publisher": "Publisher Name"
        },
        ...
      ]
    }
  }
  ```

### Get Book by ID

- **URL:** `/books/{id}`
- **Method:** `GET`
- **Response:**
  ```json
  {
    "status": "success",
    "data": {
      "book": {
        "id": "bookId",
        "name": "Name of the Book",
        "year": 2024,
        "author": "Author Name",
        "summary": "Summary of the book",
        "publisher": "Publisher Name",
        "pageCount": 300,
        "readPage": 150,
        "finished": false,
        "reading": true,
        "insertedAt": "2024-05-31T00:00:00.000Z",
        "updatedAt": "2024-05-31T00:00:00.000Z"
      }
    }
  }
  ```

### Update Book by ID

- **URL:** `/books/{id}`
- **Method:** `PUT`
- **Request Body:** Same as Add a Book
- **Response:**
  ```json
  {
    "status": "success",
    "message": "Buku berhasil diperbarui"
  }
  ```

### Delete Book by ID

- **URL:** `/books/{id}`
- **Method:** `DELETE`
- **Response:**
  ```json
  {
    "status": "success",
    "message": "Buku berhasil dihapus"
  }
  ```

## Dependencies

- `@hapi/hapi`: Framework for building web applications and services in Node.js.
- `nanoid`: Library to generate unique IDs.
