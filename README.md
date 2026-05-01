# gRPC Auth Service - SSO Server in Go

A production-ready gRPC authentication service (SSO) with full development cycle, automatic deployment, and JWT-based authorization.

## 🚀 Features

- **User Registration** - Create new accounts with hashed passwords (bcrypt)
- **JWT Authentication** - Issue and validate JWT tokens for secure access
- **gRPC API** - Modern, high-performance protocol with Protobuf contracts
- **Database Storage** - SQLite with automatic migrations
- **Graceful Shutdown** - Proper handling of SIGTERM/SIGINT signals
- **CI/CD Pipeline** - Automated deployment to cloud VM with GitHub Actions

## 📋 Tech Stack

- **Language:** Go 1.25+
- **gRPC Framework:** Google gRPC + protoc
- **Database:** SQLite (mattn/go-sqlite3)
- **Auth Tokens:** JWT (golang-jwt/jwt/v5)
- **Password Hashing:** bcrypt (golang.org/x/crypto)
- **Logging:** slog (structured JSON logs)
- **Configuration:** cleanenv
- **Middlewares:** go-grpc-middleware (recovery + logging interceptors)
- **Migrations:** golang-migrate/migrate

## 🚀 Quick Start

```bash
git clone <repository-url>
cd sso
go mod download
go build -o sso ./cmd/sso

# Run migrations
go run ./cmd/migrator --storage-path=./storage/sso.db --migrations-path=./migrations

# Start the server
CONFIG_PATH=./config/local.yaml ./sso
