# Go Movie CRUD API

A lightweight, in-memory **RESTful CRUD API** built with Go and the `gorilla/mux` router. It allows you to manage a collection of movies and their directors.

## 🚀 Features

* **Full CRUD Operations** (Create, Read, Update, Delete)
* **In-memory data store** (No database configuration required to run)
* Handles standard JSON payloads

## 🛠️ Prerequisites

* **Go** (version 1.16 or higher recommended)

## 🏃 Getting Started

1. **Clone the repository:**

   ```bash
   git clone https://github.com
   cd go-movie-crud
   ```

2. **Install dependencies:**

   ```bash
   go mod tidy
   ```

3. **Run the server:**

   ```bash
   go run main.go
   ```

   The server will start running locally at `http://localhost:8000`.

## 🛰️ API Endpoints

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| **GET** | `/movies` | Fetch all movies |
| **GET** | `/movies/{id}` | Fetch a single movie by ID |
| **POST** | `/movies` | Create a new movie (Auto-generates ID) |
| **PUT** | `/movies/{id}` | Update an existing movie by ID |
| **DELETE** | `/movies/{id}` | Delete a movie by ID |

## Request / Response Example

### Movie JSON Structure

When creating (`POST`) or updating (`PUT`) a movie, use the following JSON payload structure:

```json
{
  "isbn": "438227",
  "title": "Inception",
  "director": {
    "firstname": "Christopher",
    "lastname": "Nolan"
  }
}
```

### Quick cURL Test Command

You can test creating a movie directly from your terminal using this command:

```bash
curl -X POST http://localhost:8000/movies \
-H "Content-Type: application/json" \
-d '{"isbn":"438227","title":"Inception","director":{"firstname":"Christopher","lastname":"Nolan"}}'
```
