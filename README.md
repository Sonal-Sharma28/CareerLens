<img width="1350" height="638" alt="image" src="https://github.com/user-attachments/assets/24a7dc32-4144-4b79-8416-9ced44a9a28e" />
<img width="1361" height="631" alt="image" src="https://github.com/user-attachments/assets/5b57c993-8abc-4c0d-bd49-2de101cf1f5a" />
<img width="1361" height="620" alt="image" src="https://github.com/user-attachments/assets/8b331d82-ac5c-4705-ac11-807dae5ec1a3" />
<img width="822" height="400" alt="image" src="https://github.com/user-attachments/assets/92850601-40f1-4cd5-a686-b63da10b0fb2" />
<img width="830" height="434" alt="image" src="https://github.com/user-attachments/assets/b7604c76-5b75-4b0a-8e8e-6c800e362a24" />
<img width="835" height="427" alt="image" src="https://github.com/user-attachments/assets/fe81cf35-024d-4a0b-8580-fb2f7dd95e84" />

This is a [Next.js](https://nextjs.org) app that uses Clerk (auth), Drizzle ORM, PostgreSQL, Supabase, Hume, Arcjet, and Google Gemini.

## Quick start (Windows, cmd.exe)

Prereqs:
- Node.js 20+ and npm
- A Supabase project with PostgreSQL
- A Clerk application (Publishable + Secret keys)
- Hume API keys and a Hume configuration
- Google Gemini API key
- Arcjet key

1) Create `.env.local`

Create a `.env.local` file in the project root and add the required environment variables.

Set at least:

- `DATABASE_URL`
- `DB_HOST`
- `DB_PORT`
- `DB_USER`
- `DB_PASSWORD`
- `DB_NAME`
- `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`
- `CLERK_SECRET_KEY`
- `NEXT_PUBLIC_CLERK_SIGN_IN_URL`
- `NEXT_PUBLIC_CLERK_SIGN_IN_FALLBACK_REDIRECT_URL`
- `NEXT_PUBLIC_CLERK_SIGN_UP_FORCE_REDIRECT_URL`
- `ARCJET_KEY`
- `HUME_API_KEY`
- `HUME_SECRET_KEY`
- `NEXT_PUBLIC_HUME_CONFIG_ID`
- `GEMINI_API_KEY`
- `NEXT_PUBLIC_SUPABASE_URL`
- `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY`

Keep `.env.local` private and never commit API keys, database passwords, or other secrets to GitHub.

2) Install dependencies

```bat
npm install

3) Generate and push the database schema
npm run db:generate
npm run db:push

If you prefer applying SQL migrations:
npm run db:migrate

4)Run the development server
npm run dev
Open http://localhost:3000
Sign-in routes are configured under /sign-in and app pages under /app.

5) Notes
Clerk is used for authentication.
Drizzle ORM is used for the application's PostgreSQL database.
Supabase is used for the job-board functionality, including jobs, recruiter authentication, and applications.
Hume is used for AI-powered mock interviews.
Google Gemini is used for AI features.
Arcjet is used for request protection and feature access.
The Clerk webhook endpoint is at POST /api/webhooks/clerk.
Database configuration can be provided through DATABASE_URL or the DB_* variables.
The application uses Supabase PostgreSQL for the database connection.
Keep .env.local private and never commit credentials or API keys to GitHub.

6) Scripts
npm run dev — start Next.js development server (Turbopack)
npm run build — production build
npm run start — start the built app
npm run db:generate — generate Drizzle SQL
npm run db:push — push schema to the database
npm run db:migrate — run migrations
npm run db:studio — open Drizzle Studio


7) Troubleshooting
Database connection error: Check DATABASE_URL and the DB_* variables in .env.local.
Authentication issues: Check that the Clerk Publishable and Secret keys are correctly configured.
Hume interview not working: Check HUME_API_KEY, HUME_SECRET_KEY, and NEXT_PUBLIC_HUME_CONFIG_ID.
Job board not loading: Check NEXT_PUBLIC_SUPABASE_URL and NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY.
Environment validation errors: Check the required variables in .env.local.
Environment variable changes not taking effect: Stop the development server with Ctrl + C and run npm run dev again.
