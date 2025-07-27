# Go-Next.js-BetterAuth-Tailwind Webapp Template

This template provides a basic setup for a web application using:

- **Backend:** Go with Chi router
- **Frontend:** Next.js with React and Tailwind CSS
- **Authentication:** Better Auth

## Project Structure

```
my-webapp/
├── backend/             # Go backend application
│   └── main.go
├── frontend/            # Next.js frontend application
│   ├── public/
│   ├── app/
│   │   ├── api/
│   │   │   └── auth/
│   │   │       └── [...all]/route.ts
│   │   ├── globals.css
│   │   ├── layout.tsx
│   │   └── page.tsx
│   └── lib/
│       ├── auth.ts
│       └── auth-client.ts
│   ├── package.json
│   ├── tailwind.config.ts
│   └── tsconfig.json
└── README.md
```

## Setup and Running the Project

### 1. Clone the Repository (or use this template)

If you're using this as a new project, you can copy the `my-webapp` directory.

### 2. Backend Setup (Go)

Navigate to the `backend` directory:

```bash
cd my-webapp/backend
```

Initialize the Go module and download dependencies:

```bash
go mod init my-webapp-backend # Only if you haven't already
go mod tidy
```

Run the backend server:

```bash
go run main.go
```

The Go backend will run on `http://localhost:8080`.

### 3. Frontend Setup (Next.js)

Navigate to the `frontend` directory:

```bash
cd my-webapp/frontend
```

Install Node.js dependencies:

```bash
npm install
```

#### Environment Variables

Create a `.env.local` file in the `frontend` directory:

```
BETTER_AUTH_SECRET=YOUR_BETTER_AUTH_SECRET
BETTER_AUTH_URL=http://localhost:3000
```

**Important:** Replace `YOUR_BETTER_AUTH_SECRET` with a strong, randomly generated secret. You can generate one using `openssl rand -base64 32`.

#### Database Migration

Run the Better Auth database migration (this will create `database.sqlite`):

```bash
npx @better-auth/cli@latest migrate
```

When prompted, type `y` and press Enter to confirm the migration.

#### Run the Frontend

```bash
npm run dev
```

The Next.js frontend will run on `http://localhost:3000`.

## Testing Authentication

1.  Ensure both the Go backend (`go run main.go`) and Next.js frontend (`npm run dev`) are running.
2.  Open your browser and go to `http://localhost:3000`.
3.  Use the provided sign-up form to create a new user.
4.  Test signing in and signing out.

## Customization

-   **Go Backend:** Modify `backend/main.go` to add more API endpoints and logic.
-   **Next.js Frontend:** Customize `frontend/app/page.tsx` and other components. Tailwind CSS is already configured for styling.
-   **Better Auth:** Refer to the [Better Auth documentation](https://www.better-auth.com/docs/introduction) for advanced authentication features, social logins, and more database options.
