# Next.js + Prisma + AuthJS Starter Template

A modern full-stack starter template built with Next.js 14, Prisma, and AuthJS (NextAuth). Features TypeScript, Tailwind CSS, and shadcn/ui components out of the box.

## Features

- 🚀 [Next.js 14](https://nextjs.org/) with App Router
- 🔐 Authentication with [AuthJS](https://authjs.dev/) (formerly NextAuth)
  - Google OAuth provider
  - Email/Password authentication
  - JWT strategy
- 🗃️ [Prisma](https://www.prisma.io/) as ORM
  - PostgreSQL database
  - Authentication models included
- 🎨 Styling and UI
  - [Tailwind CSS](https://tailwindcss.com/)
  - [shadcn/ui](https://ui.shadcn.com/) components
  - [Geist](https://vercel.com/font) font family
- 🐳 Docker Compose setup for PostgreSQL
- 📦 [pnpm](https://pnpm.io/) as package manager

## Getting Started

### Prerequisites

- Node.js 18+ 
- pnpm
- Docker (for PostgreSQL)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/BlitzJB/next-prisma-authjs-starter.git
cd next-prisma-authjs-starter
```

2. Install dependencies:
```bash
pnpm install
```

3. Set up your environment variables:
```bash
cp .env.example .env
```

4. Update the following variables in your `.env`:
- `NEXTAUTH_SECRET` (Generate with: `openssl rand -base64 32`)
- `GOOGLE_CLIENT_ID`
- `GOOGLE_CLIENT_SECRET`

5. Start the PostgreSQL database:
```bash
docker-compose up -d
```

6. Run database migrations:
```bash
npx prisma migrate dev
```

7. Start the development server:
```bash
pnpm dev
```

Visit `http://localhost:3000` to see your application.

## Authentication Setup

### Google OAuth

1. Go to the [Google Cloud Console](https://console.cloud.google.com)
2. Create a new project or select an existing one
3. Enable the Google+ API
4. Create OAuth 2.0 credentials
5. Add authorized redirect URI: `http://localhost:3000/api/auth/callback/google`
6. Copy the client ID and secret to your `.env` file

### Email/Password Authentication

The template includes email/password authentication out of the box. Users can:
- Register with email and password
- Sign in with existing credentials
- Password hashing using bcrypt

## Project Structure

```
.
├── app/                    # Next.js App Router
│   ├── api/               # API routes
│   │   └── auth/         # AuthJS configuration
│   ├── auth/             # Authentication pages
│   └── ...               # Other app routes
├── lib/                   # Utility functions
├── prisma/               # Prisma schema and migrations
│   └── schema.prisma     # Database schema
└── docker-compose.yml    # Docker configuration
```

## Database Schema

The template includes the following models:
- `User`: Core user model with auth fields
- `Account`: OAuth accounts
- `Session`: User sessions
- `VerificationToken`: Email verification

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [Next.js](https://nextjs.org/)
- [Prisma](https://www.prisma.io/)
- [AuthJS](https://authjs.dev/)
- [shadcn/ui](https://ui.shadcn.com/)
