# Chirpy - Social Media Backend

A Twitter-like social media backend API built with Go, featuring user authentication, chirp (tweet) management, and webhook integration.

## Features

- 🔐 User Authentication & Authorization
  - JWT-based authentication
  - Login and refresh token endpoints
  - Password hashing and validation

- 📝 Chirp Management
  - Create, read, and delete chirps
  - Rate limiting
  - User-specific chirp operations

- 🔄 Webhook Integration
  - Real-time event notifications
  - Webhook management endpoints

- 📊 Additional Features
  - File serving capabilities
  - Metrics tracking
  - Health check endpoints
  - Database integration with PostgreSQL

## Tech Stack

- Go (Backend)
- PostgreSQL (Database)
- SQLC (SQL Query Generator)
- JWT (Authentication)

## Project Structure

```go
.
├── assets/          // Static assets
├── internal/        // Internal packages
├── sql/             // Database queries and migrations
├── handlers/        // HTTP request handlers
└── main.go          // Application entry point
```

## API Endpoints

### Authentication

- POST /api/login
- POST /api/refresh

### Users

- POST /api/users
- PUT /api/users

### Chirps

- POST /api/chirps
- GET /api/chirps
- DELETE /api/chirps/{id}

### Webhooks

- POST /api/webhooks

## Getting Started

### Prerequisites

- Go 1.19 or higher
- PostgreSQL
- Git

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/deedee-ke/chirpy.git
   cd chirpy
   ```

2. Install dependencies:
   ```bash
   go mod download
   ```

3. Set up the database:
   ```sql
   # Create PostgreSQL database
   psql -U postgres
   CREATE DATABASE chirpy;

   # Run migrations
   # [Add your migration command here]
   ```

4. Configure environment variables:
   ```bash
   # Create a .env file in the root directory
   touch .env

   # Add the following variables
   DB_URL=postgres://username:password@localhost:5432/chirpy?sslmode=disable
   JWT_SECRET=your_jwt_secret
   PORT=8080
   ```

5. Run the server:
   ```bash
   go run .
   ```
   The server will start at http://localhost:8080

## Development

To run the project in development mode with hot reload:

```bash
go run main.go
```

## Testing

Run the test suite:

```bash
go test ./...
```

## Building for Production

1. Build the binary:
   ```bash
   go build -o chirpy
   ```

2. Run the compiled binary:
   ```bash
   ./chirpy
   ```

## API Usage

### Authentication

To access protected endpoints, include the JWT token in the Authorization header:

```http
Authorization: Bearer <your_jwt_token>
```

### Rate Limiting

API endpoints are rate-limited to:

- 10 requests per second for authenticated users
- 5 requests per second for unauthenticated users

## Contributing

1. Fork the repository
2. Create your feature branch:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. Commit your changes:
   ```bash
   git commit -m 'Add some amazing feature'
   ```
4. Push to the branch:
   ```bash
   git push origin feature/amazing-feature
   ```
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

## Acknowledgments

- Boot.dev for project inspiration
- Contributors and maintainers

