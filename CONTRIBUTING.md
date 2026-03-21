# Contributing

Thank you for considering a contribution to this project. Please read the guidelines below before opening a branch or pull request.

## Branch Naming

All branches must use one of the following prefixes:

| Prefix | Purpose |
|---|---|
| `feat/` | New features or enhancements |
| `fix/` | Bug fixes |
| `chore/` | Maintenance, dependency updates, config changes |
| `test/` | Adding or updating tests only |
| `security/` | Security patches or hardening |

**Examples**

```
feat/user-profile-page
fix/comment-like-count
chore/update-tailwind
test/blog-policy-coverage
security/sanitize-tag-input
```

## Commit Messages

This project follows the [Conventional Commits](https://www.conventionalcommits.org/) specification.

```
<type>(<scope>): <short description>

[optional body]

[optional footer]
```

**Types:** `feat`, `fix`, `chore`, `test`, `security`, `docs`, `refactor`, `perf`, `ci`

**Examples**

```
feat(blog): add draft visibility toggle
fix(comments): prevent duplicate like on refresh
chore(deps): upgrade inertia-laravel to v2.1
test(api): add coverage for organization invite flow
security(auth): enforce rate limiting on login endpoint
```

- Use the imperative mood in the subject line: "add feature" not "added feature"
- Keep the subject line under 72 characters
- Reference issues in the footer: `Closes #42`

## Pull Request Checklist

Before marking a PR as ready for review, confirm the following:

- [ ] Tests have been written or updated to cover the change
- [ ] `vendor/bin/pint --dirty --format agent` has been run and all PHP files are formatted
- [ ] No `env()` calls exist outside of `config/` files — use `config()` instead
- [ ] If any routes were added, removed, or renamed, Wayfinder types have been regenerated (`php artisan wayfinder:generate`)
- [ ] No commented-out code or debugging statements left in the diff
- [ ] The PR targets the correct base branch

## Development Setup

```bash
composer install
npm install
cp .env.example .env
php artisan key:generate
php artisan migrate
npm run build
```

Run tests:

```bash
php artisan test --compact
```
