# RIWI Sportsline Backend

This repository contains the backend service for **RIWI Sportsline**, a sports equipment e commerce platform built with [NestJS](https://nestjs.com/). The project is modular and follows the layered architecture recommended by NestJS. It uses **TypeORM** to persist data in a relational database and includes robust authentication/authorization mechanisms, middleware, filters, interceptors, testing, and static analysis.

## Project Features

- **Modular Architecture:** The app is organized into modules (`auth`, `users`, `roles`, `permissions`, `products`, `orders`, `clients`, etc.) to promote separation of concerns and maintainability.
- **RESTful API:** Each module exposes controllers with typed **DTOs** (data transfer objects) for input validation using `class-validator` and `class-transformer`.
- **TypeORM Integration:** Entities map to database tables. Repositories/services provide database access with proper relations between users, roles, products, orders, clients, etc.
- **Authentication & Authorization:**
  - **JWT** support with access and refresh tokens.
  - **Roles and permissions** extracted from the database and checked via custom decorators and guards.
  - **Local strategy** for username/password login and **Google OAuth** strategy for social login.
  - **API key** guard for simple token based access to specific endpoints.
- **Middleware, Filters & Interceptors:**
  - Logging middleware to track incoming requests.
  - Global HTTP exception filter to return structured error responses.
  - Response and timeout interceptors to wrap results and enforce timeouts.
- **Security:** Secure password hashing, environment‑based configuration, validation schemas, and CORS configuration.
- **Testing:** Example unit tests using Jest are provided (e.g., `users.service.spec.ts`). You can add more unit/integration tests to ensure code quality.
- **Static Analysis:** ESLint and Prettier are configured along with Husky hooks to run linters and tests before committing.
- **Documentation:** The API is documented with **Swagger** (OpenAPI). After running the app, navigate to `/api` to view interactive docs.

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18 or later
- [Nest CLI](https://docs.nestjs.com/cli/overview) (optional for running CLI commands)
- A relational database supported by TypeORM (e.g., PostgreSQL). Update `src/config/configuration.ts` with your DB credentials or set the relevant environment variables.

### Installation

1. **Clone the repository** and switch to the desired branch (e.g., `main`, `hu1`, …).

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run database migrations** (if using migrations) or ensure the entities are synced automatically via TypeORM settings.

4. **Start the development server**:
   ```bash
   npm run start:dev
   ```

5. Visit `http://localhost:3000/api` to explore the Swagger documentation.

### Running Tests

Run unit tests with Jest:
```bash
npm run test
```

## Branching Strategy

Branches are organised by **HU (historias de usuario)**. Each HU branch contains the same project code (stored as a zip in this repository) with a commit message describing the implemented feature. You can switch to any branch to review the code associated with that user story.

## Contributing

1. Fork the repository and create your feature branch: `git checkout -b feature/AmazingFeature`.
2. Commit your changes: `git commit -m 'Add some AmazingFeature'`.
3. Push to the branch: `git push origin feature/AmazingFeature`.
4. Open a pull request.

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
