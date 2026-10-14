# Plant Maintenance Management System

A **plant & equipment maintenance management system (CMMS)** built on **Laravel 12 + Filament 3.3**,
intended to manage work orders, preventive maintenance schedules and plant asset history.

---

## ⚠️ Repository status

**This repository currently contains only the Laravel project skeleton — no application code.**

The committed tree is limited to the framework scaffolding:

```
.editorconfig      .env.example       .gitignore
.env               .htaccess          artisan
.gitattributes     composer.json      composer.lock
package.json       phpunit.xml        vite.config.js
```

There is no `app/`, `database/`, `routes/`, `resources/` or `public/` directory, so the application
cannot be run from this repository as it stands.

**If you arrived here expecting a working CMMS: the source has not been published yet.**
The full application exists locally and still needs to be pushed.

---

## Intended scope

| Area | Description |
|------|-------------|
| **Work orders** | Raise, assign, prioritise and close maintenance work orders |
| **Preventive maintenance** | Recurring schedules by machine, meter reading or calendar interval |
| **Asset register** | Plant and equipment records with location and criticality |
| **Breakdowns** | Downtime logging and root-cause notes |
| **Spare parts** | Parts consumption against work orders |
| **History** | Full maintenance history per asset |
| **Reporting** | MTTR / MTBF and maintenance cost reporting |

---

## Planned stack

| Layer | Technology |
|-------|-----------|
| Framework | Laravel 12 (PHP 8.2+) |
| Admin panel | Filament 3.3 |
| Seeding | orangehill/iseed |
| Database | MySQL |
| Frontend | Blade + Vite |

---

## Running it (once the application code is pushed)

```bash
composer install
npm install

cp .env.example .env
php artisan key:generate
# set DB_* in .env

php artisan migrate --seed

npm run build
php artisan serve
```

---

## 🚨 Security note

The committed `.env` file must be removed from version control and its contents rotated:

- `APP_KEY` — rotatable with `php artisan key:generate`
- `MAIL_PASSWORD` — a live **Gmail app password**. It must be revoked in the Google account and a
  new one issued, then stored only in an untracked `.env`.

`.env` is already listed in `.gitignore`, but it was committed **before** that line existed, so Git
continues to track it. Untrack it with:

```bash
git rm --cached .env
git commit -m "Stop tracking .env"
```

Note that this removes the file going forward but does **not** erase it from history — the
credential must be revoked regardless.

---

## License

Proprietary — not licensed for redistribution.
