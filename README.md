# Community Resource Finder

A React and TypeScript app for finding food assistance in Utah by city, including
pantries, vouchers, and hot meals. Results show contact information, hours,
eligibility, and map links.

## Highlights

- City-based search with resource cards and contact details.
- Typed Supabase client backed by a normalized PostgreSQL schema.
- Row-level security policies for public reads and restricted writes.
- Built-in sample data when the backend is not configured or available.
- SQL migrations and sample food-resource seed data.

[Watch the project walkthrough](databaseprojectdemo.mp4).

## Run locally

Requires Node.js and npm. The sample-data mode works without a Supabase account.

```sh
npm ci
npm run dev
```

Open the URL printed by Vite and search for a Utah city.

To connect your own Supabase project, copy `.env.example` to `.env`,
fill in the two public client settings, and apply the SQL in `supabase/migrations/`
and `supabase/seeds/` to your database. Never put a service-role key in the frontend.

## Checks and build

```sh
npm run typecheck
npm run build
```

## Structure

| Directory | Purpose |
| --- | --- |
| src/components | Search input and resource cards |
| src/hooks/useResources.ts | Data loading, filtering, and sample fallback |
| src/lib | Supabase client and generated database types |
| supabase/migrations | Schema, access policies, and vector extension setup |
| supabase/seeds | Sample resource records |

The embeddings table prepares for future semantic search; the current interface
searches by city. This is a database course project with documented AI assistance
for copy and refactoring; see [the project report](FINAL_REPORT.md).
