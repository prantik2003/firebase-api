
# User Management and Notes API

This README provides an overview of the Firestore database structure used in the project. The database is organized into two main collections: users and notes. These collections are designed to manage user profiles and personal notes efficiently.


## Database structure and API reference

#### Get all users

```http
  GET /api/users
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get user

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of user to fetch |

#### Get all notes

```http
  GET /api/notes
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get note

```http
  GET /api/notes/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of note to fetch |

#### Add note

```http
  POST /api/notes
```
| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `userId`      | `string` | **Required**. Id of the user who created the note |
| `title`      | `string` | **Required**. Title of the note |
| `content`      | `string` | **Required**. Detailed content of the note |
| `timestamp`      | `string` | **Required**. ISO 8601 formatted timestamp of the note |


#### Example of adding a note

```json
  {
  "userId": "user-12345",
  "title": "Grocery List",
  "content": "Milk, Eggs, Bread, Butter",
  "timestamp": "2024-11-19T12:00:00Z"
  }
```

## Postman Collection

1. Get Data API

--> Endpoint: http://localhost:4000/getuser

--> Example Body: N/A (No body for GET request)

2. Post Data API

--> Endpoint: http://localhost:4000/createuser

--> Example Body: 
```json
  {
  "email": "test@example.com",
  "name": "Test User",
  "age": 25
  }
```

3. Update  Data API

--> Endpoint: http://localhost:4000/updateuser

--> Example Body: 
```json
  {
  "email": "test@example.com",
  "updateData": { "name": "Updated User" }
  }
```

4. Delete  Data API

--> Endpoint: http://localhost:4000/deleteuser

--> Example Body: N/A (No body for DELETE request)

5. Save Note API

--> Endpoint: http://localhost:4000/savenote

--> Example Body: 
```json
  {
  "userId": "user-12345",
  "title": "Sample Note",
  "content": "This is a test note."
  }
```

6. Get Note API

--> Endpoint: http://localhost:4000/getnotes?userId=user-12345

--> Example Body: N/A (Query parameter only for GET request)
