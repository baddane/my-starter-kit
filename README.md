# Starter Kit

A production-ready Next.js starter template with a full-stack setup.

## Stack

- **Framework**: Next.js 16 (App Router) + React 19
- **Language**: TypeScript (strict mode)
- **Database**: PostgreSQL via Supabase
- **ORM**: Prisma
- **UI**: Tailwind CSS v4 + Shadcn/ui (via `npx shadcn add <component>`)
- **Validation**: Zod
- **Icons**: lucide-react

## Getting Started

### 1. Clone & install

```bash
git clone <your-repo-url>
cd <your-project>
npm install
```

### 2. Configure environment

```bash
cp .env.example .env.local
```

Fill in your values in `.env.local`:

```env
DATABASE_URL="postgres://postgres:[PASSWORD]@db.[REF].supabase.co:6543/postgres?pgbouncer=true"
NEXT_PUBLIC_SUPABASE_URL="https://[REF].supabase.co"
NEXT_PUBLIC_SUPABASE_ANON_KEY="your-anon-key"
```

### 3. Set up the database

```bash
npm run db:migrate   # run migrations
npm run db:generate  # generate Prisma client
```

### 4. Start the dev server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

---

## Project Structure

```
src/
├── app/              # Routes and pages (Next.js App Router)
├── components/
│   └── ui/           # Shadcn/ui components (add via CLI)
└── lib/
    ├── db.ts         # Prisma client singleton
    ├── supabase.ts   # Supabase client
    └── utils.ts      # cn() utility (clsx + tailwind-merge)
prisma/
└── schema.prisma     # Database schema
```

## Database Scripts

| Command | Description |
|---------|-------------|
| `npm run db:migrate` | Run pending migrations |
| `npm run db:generate` | Regenerate Prisma client |
| `npm run db:push` | Push schema without migration (prototyping) |
| `npm run db:studio` | Open Prisma Studio |
| `npm run db:reset` | Reset the database |

## Adding Shadcn/ui Components

```bash
npx shadcn add button
npx shadcn add input
npx shadcn add card
# etc.
```

Components are generated into `src/components/ui/`.

## Code Style

```bash
npm run lint     # ESLint
npm run format   # Prettier
```
