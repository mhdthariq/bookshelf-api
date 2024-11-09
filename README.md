# Bookshelf API

## About
Bookshelf API is a simple RESTful API for managing a collection of books. This API allows users to:
- **Search** for books by name, reading status, and finished status.
- **Add** new books to the collection.
- **Update** existing books.
- **Delete** books from the collection.

The API is built using the **Hapi.js** framework and supports various query parameters for filtering books.

## Features
- **GET /books**: Retrieve all books with optional query parameters for filtering:
  - `name`: Search books by name (case-insensitive).
  - `reading`: Filter books by reading status (0 for not reading, 1 for reading).
  - `finished`: Filter books by finished status (0 for not finished, 1 for finished).
  
- **POST /books**: Add a new book to the collection.
  
- **GET /books/{id}**: Retrieve a specific book by its ID.
  
- **PUT /books/{id}**: Update an existing book's information by ID.
  
- **DELETE /books/{id}**: Delete a book by its ID.

## Installation

### Prerequisites
- **Node.js**: Ensure that you have Node.js installed. You can download it from [here](https://nodejs.org/).

### Steps to Install
1. Clone the repository:
   ```bash
   git clone https://github.com/mhdthariq/bookshelf-api.git
   ```

2. Navigate to the project directory:
   ```bash
   cd bookshelf-api
   ```

3. Install the dependencies:
   ```bash
   npm install
   ```

## Usage

### Running the Development Server

To run the server in development mode with auto-reload, use:

```bash
npm run start-dev
```

The API will start on `http://localhost:9000`.

### Running the Production Server

To run the server in production mode, use:

```bash
npm start
```

### Linting

To check for linting issues in your code, run:

```bash
npm run lint
```

## Endpoints

### `GET /books`
Retrieve all books with optional query parameters:
- **`name`**: (optional) Search for books by name (case-insensitive).
- **`reading`**: (optional) Filter books by reading status (1 for reading, 0 for not reading).
- **`finished`**: (optional) Filter books by finished status (1 for finished, 0 for not finished).

**Example:**
```http
GET /books?name=dicoding
```

### `POST /books`
Add a new book to the collection. The request body should contain the following fields:
- `name`: The name of the book (required).
- `year`: The year of publication (optional).
- `author`: The author of the book (optional).
- `summary`: A brief summary of the book (optional).
- `publisher`: The publisher of the book (optional).
- `pageCount`: The total number of pages in the book (optional).
- `readPage`: The number of pages already read (optional).
- `reading`: Whether the book is currently being read (true/false).

**Example:**
```http
POST /books
{
  "name": "Dicoding Guide",
  "year": 2024,
  "author": "John Doe",
  "summary": "A guide to learning web development.",
  "publisher": "Dicoding",
  "pageCount": 300,
  "readPage": 150,
  "reading": true
}
```

### `GET /books/{id}`
Retrieve a specific book by its ID.

**Example:**
```http
GET /books/12345
```

### `PUT /books/{id}`
Update an existing book by its ID. The request body should contain the fields you wish to update.

**Example:**
```http
PUT /books/12345
{
  "name": "Updated Book Name",
  "year": 2025,
  "author": "Jane Doe",
  "summary": "Updated summary",
  "publisher": "Updated Publisher",
  "pageCount": 350,
  "readPage": 200,
  "reading": false
}
```

### `DELETE /books/{id}`
Delete a specific book by its ID.

**Example:**
```http
DELETE /books/12345
```
