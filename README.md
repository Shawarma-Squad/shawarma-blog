# shawarma.blog

A focused microblogging platform built with Laravel, Inertia.js, and React. Users can publish short posts, follow each other, react to content, leave comments, and collaborate inside organisations — all wrapped in a clean, fast SPA experience.

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | PHP 8.2 · Laravel 12 · Laravel Fortify |
| Frontend | React 19 · TypeScript · Inertia.js v2 |
| Styling | Tailwind CSS v4 · Radix UI · Headless UI |
| Editor | Lexical rich-text editor |
| Routing | Laravel Wayfinder (type-safe route bindings) |
| Notifications | Novu |
| Email | Resend |
| Queue / Cache | Redis (Predis) |
| File Storage | AWS S3 (via Flysystem) |
| Access Control | Invite-only registration |
| Testing | Pest 4 · PHPUnit 12 |

## Requirements

- PHP 8.2+
- Composer
- Node.js 20+ & npm
- A database supported by Laravel (MySQL, PostgreSQL, SQLite)
- Redis (for queues and cache)

## Getting Started

### 1. Clone and install dependencies

```bash
git clone https://github.com/your-org/shawarma-blog.git
cd shawarma-blog

composer install
npm install
```

### 2. Configure environment

```bash
cp .env.example .env
php artisan key:generate
```

Edit `.env` and set your database, Redis, mail (Resend), S3, and Novu credentials.

### 3. Run migrations

```bash
php artisan migrate
```

### 4. Start the development server

```bash
composer run dev
```

This starts the Laravel server, queue worker, log tail (Pail), and Vite dev server concurrently.

The application will be available at **http://localhost:8000**.

## Available Scripts

### PHP / Composer

| Command | Description |
|---|---|
| `composer run dev` | Start all dev processes concurrently |
| `composer run setup` | Full first-run setup (install, migrate, build) |
| `php artisan test --compact` | Run the test suite |
| `vendor/bin/pint --dirty` | Fix PHP code style (Laravel Pint) |
| `php artisan wayfinder:generate` | Regenerate TypeScript route bindings |

### Node / npm

| Command | Description |
|---|---|
| `npm run dev` | Start Vite dev server only |
| `npm run build` | Production asset build |
| `npm run lint` | ESLint with auto-fix |
| `npm run format` | Prettier formatting |
| `npm run types` | TypeScript type check |

## Key Features

- **Microblogging** — create and publish short posts with rich-text via the Lexical editor
- **Visibility control** — posts can be public, unlisted, or private
- **Organisations** — create organisations, invite members, and publish collaborative content
- **Social graph** — follow users and see a personalised feed
- **Reactions & comments** — like posts and leave threaded comments
- **Tags** — categorise and discover posts by topic
- **Invite-only registration** — controlled access via invitation links
- **Notifications** — in-app and email notifications powered by Novu and Resend
- **Two-factor authentication** — TOTP 2FA via Laravel Fortify

## Project Structure

```
app/
  Http/Controllers/   # Inertia + API controllers
  Models/             # Eloquent models (Blog, Comment, Like, Follow, Tag, Organisation, User)
  Policies/           # Authorization policies
  Enums/              # PostVisibility, LikeType, OrganisationRole
  Services/           # NovuService
  Jobs/               # Queued jobs (notifications, subscriber sync)
resources/js/
  pages/              # Inertia page components
  components/         # Shared React components
  layouts/            # Page layouts
  hooks/              # Custom React hooks
  lib/                # Utility modules
routes/
  web.php             # Main application routes
  settings.php        # Settings-related routes
  console.php         # Scheduled commands
```

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request.

## License

This project is open-source software licensed under the [MIT licence](LICENSE).
