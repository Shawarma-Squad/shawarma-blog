## Summary

<!-- Describe the change and the motivation behind it. Link to any related issues. -->

Closes #

## Testing

<!-- Describe how the change was tested. Which test file(s) cover this? -->

```bash
php artisan test --compact --filter=
```

## Screenshots

<!-- Include before/after screenshots for UI changes. Delete this section if not applicable. -->

## Checklist

- [ ] Tests added or updated, and passing
- [ ] `vendor/bin/pint --dirty --format agent` run — PHP files are correctly formatted
- [ ] No `env()` calls outside of `config/` files
- [ ] Wayfinder types regenerated (`php artisan wayfinder:generate`) if routes were added, removed, or renamed
- [ ] No debug statements or commented-out code left in the diff
- [ ] PR targets the correct base branch
