# 📚 Book Store API (NestJS)

A production-ready REST API built with **NestJS**, **TypeORM**, and **Class Validator** for managing books.

---

## 🚀 Features

- 📖 CRUD operations for Books
- ✅ Request validation using DTOs
- 🛡️ Clean architecture (Modular NestJS structure)
- 🗄️ Database integration with TypeORM
- ⚡ Fast development setup with hot reload
- ❌ Global error handling & validation pipes

---

## 🧱 Tech Stack

| Technology | Purpose |
|---|---|
| NestJS | Backend framework |
| TypeScript | Type safety |
| TypeORM | Database ORM |
| PostgreSQL / MySQL | Database (configurable) |
| Class Validator | DTO-based validation |
| Class Transformer | Object transformation |

---

## 📁 Project Structure

```
src/
│
├── common/
│   ├── constants/
│   │   └── message.ts
│   ├── entities/
│   │   └── base.entity.ts
│   ├── enums/
│   │   └── crud.enum.ts
│   ├── exceptions/
|   |   ├── exception.ts
│   │   └── http.exception.ts
│   ├── logger/
│   │   └── custom-logger.ts
│   └── middleware/
│       └── logger.middleware.ts
|
├── modules/books
│   ├── dto/
|   |   ├── update-book.dto.ts
│   │   └── create-book.dto.ts
│   ├── entities/
│   │   └── book.entity.ts
│   ├── books.controller.ts
│   ├── books.service.ts
│   └── books.module.ts
│
├── database/
│   ├── entities/
│   │   └── index.entity.ts
│   └── db.service.ts
│
├── app.controller.ts
├── app.module.ts
├── app.service.ts
└── main.ts
```

---

## ⚙️ Installation

```bash
# Clone the project
git clone <your-repo-url>

# Move into project
cd book_store_demo_node

# Install dependencies
npm install
```

---

## 🔐 Environment Variables

Create a `.env` file in the root directory:

```env
DB_URL=your_url
PORT=3000
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=your_password
DB_NAME=book_store
```

---

## ▶️ Running the Application

### Development mode

```bash
npm run start:dev
```

### Production mode

```bash
npm run build
npm run start:prod
```

---

## 📌 API Endpoints

### 📚 Books Routes

| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/books` | Create a book |
| `GET` | `/books` | Get all books |
| `GET` | `/books/:id` | Get book by ID |
| `PUT` | `/books/:id` | Update book |
| `DELETE` | `/books/:id` | Delete book |

---

## 📤 Create Book Example

**Request**

```http
POST /books
Content-Type: application/json
```

**Body**

```json
{
  "bookName": "Clean Code",
  "isbn": "9780132350884"
}
```

**Response**

```json
{
  "id": 1,
  "bookName": "Clean Code",
  "isbn": "9780132350884"
}
```

---

## ❗ Validation Rules

- `bookName` → Required, must not be empty
- `isbn` → Required, must be exactly 13 characters

---

## 🧪 Error Response Example

```json
{
  "statusCode": 400,
  "timestamp": "2026-05-06T08:00:15.658Z",
  "path": "/books",
  "message": [
    "bookName should not be empty",
    "isbn must be longer than or equal to 13 characters"
  ],
  "success": false
}
```

---

## 🏗️ Architecture Overview

```
Controller  →  Handles HTTP requests
Service     →  Business logic
DTO         →  Validation layer
Entity      →  Database schema
Module      →  Feature isolation
```

---

## 🔥 Production Best Practices

- DTO-based validation
- Modular structure
- Environment-based configuration
- Type safety with TypeScript
- Clean separation of concerns

---

## 🚀 Future Improvements

- [ ] JWT Authentication
- [ ] Role-based access control (Admin/User)
- [ ] Swagger API documentation
- [ ] Docker support
- [ ] CI/CD pipeline
- [ ] Logging (Winston / Pino)

---

## 👨‍💻 Author

Built with ❤️ using NestJS

---

## 📄 License

[MIT](LICENSE)