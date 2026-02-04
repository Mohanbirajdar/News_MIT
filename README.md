# News_MIT (Laravel)

Simple news portal built with Laravel.

**Project overview**
- Framework: Laravel 11
- PHP: ^8.1
- Database: MySQL (or compatible)
- Frontend tooling: Vite, Tailwind CSS, Alpine.js
- Packages: spatie/laravel-permission, laravel/sanctum, realrashid/sweet-alert, laravel/tinker

## Tech stack

- PHP 8.1+
- Laravel 11
- MySQL
- Vite
- Tailwind CSS
- Alpine.js
- Composer
- Node / npm

## Notable packages

- `spatie/laravel-permission` — roles & permissions
- `laravel/sanctum` — API auth and token management
- `realrashid/sweet-alert` — alert notifications

## Quick setup

1. Clone the repo
2. Install PHP dependencies:

```
composer install
```

3. Install Node dependencies and build assets:

```
npm install
npm run dev
```

4. Copy `.env` and update values (DB, APP_URL):

```
cp .env.example .env
php artisan key:generate
```

5. Configure `.env` DB settings (see existing `.env` for defaults). Run migrations:

```
php artisan migrate
```

6. Optionally seed users (if seeders exist):

```
php artisan db:seed
```

7. Run the application:

```
php artisan serve --host=127.0.0.1 --port=8000
```

## Project structure (top-level)

- `app/` — application code (Models, Http, Providers, Mail, etc.)
- `config/` — config files
- `database/` — migrations, seeders, factories
- `resources/` — views, CSS, JS
- `routes/` — route definitions (`web.php`, `admin.php`, `api.php`)
- `public/` — web root

## Environment

Example `.env` shows `APP_URL` set to `http://news-portal.test/`. Replace with your host when deploying.

## Credentials

Admin Logins:
url:{your host}/admin/login
email: admin@gmail.com
password: password

User Logins:
email: user123@gmail.com
password: 12345678

Writer Logins:
url:{your host}/admin/login
email: writer@gmail.com
password: 12345678

---

If you want, I can:
- run the app locally (`php artisan serve`) and confirm the admin route
- create seeders to insert the above users (requires deciding roles and hashing)
- commit the `README.md` for you
<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 2000 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[OP.GG](https://op.gg)**
- **[WebReinvent](https://webreinvent.com/?utm_source=laravel&utm_medium=github&utm_campaign=patreon-sponsors)**
- **[Lendio](https://lendio.com)**
# News_MIT — Laravel News Portal

This is a news portal built with Laravel. It provides a public-facing frontend for browsing news and an admin panel for managing content, settings, and localization.

## Summary / Project overview

- Framework: Laravel 11
- PHP: ^8.1
- Database: MySQL (or compatible)
- Frontend tooling: Vite, Tailwind CSS, Alpine.js
- Auth scaffolding: Laravel Breeze (parts present)
- Important packages: `spatie/laravel-permission`, `laravel/sanctum`, `realrashid/sweet-alert`

This `README.md` includes the original quick-start notes plus a comprehensive feature list and setup instructions.

## Features (what the project provides)

- Public frontend:
	- Home page with hero slider, breaking news, recent & popular news, and category sections.
	- News list with pagination, filtering by category, tag, and search.
	- News detail page with author, tags, related posts, next/previous navigation, view counts, and comments with replies.
	- Newsletter subscription endpoint.
	- Contact page with form that sends email and stores messages.
	- Static About page.
	- Language switcher / localization support.

- Admin panel (prefixed with `/admin`):
	- Admin authentication (login, logout, forgot/reset password).
	- Dashboard overview.
	- CRUD for `News`, including status toggles, approval workflow, copy/duplicate news, and pending news listing.
	- CRUD for `Category`.
	- Home section settings to configure which categories appear in home sections.
	- Social counts and social links management.
	- Ads management.
	- Subscriber list management.
	- Footer content management (footer grids, titles, and info).
	- About page content management.
	- Contact page settings and contact-message inbox + reply functionality.
	- General, SEO, appearance, and Microsoft API settings.
	- Roles & permissions management using `spatie/laravel-permission`.
	- Admin user management (role assignment & CRUD).
	- Localization tools: extract strings, update language strings, and translate strings via admin UI.
	- Profile management for admin users (update profile, change password).

- Other features & utilities:
	- Comment submission, reply, and deletion (with authorization checks).
	- View counter with session-based duplicate view protection.
	- Tag aggregation and most common tags calculation.
	- Mail sending via configured SMTP (Mailtrap in `.env` example) and storing received contact mails.

## Notable Code Locations

- Routes: `routes/web.php`, `routes/admin.php`, `routes/api.php` (if present)
- Frontend controller: `app/Http/Controllers/Frontend/HomeController.php`
- Admin controllers: `app/Http/Controllers/Admin/*` (many resources: `NewsController`, `CategoryController`, etc.)
- Models: `app/Models/*` (`News`, `Category`, `Comment`, `Subscriber`, `Ad`, `Setting`, etc.)
- Views: `resources/views/frontend` and `resources/views/admin` (blade templates)

## Quick setup (original content included)

1. Clone the repo
2. Install PHP dependencies:

```bash
composer install
```

3. Install Node dependencies and build assets:

```bash
npm install
npm run dev
```

4. Copy `.env` and update values (DB, APP_URL):

```bash
cp .env.example .env
php artisan key:generate
```

5. Configure `.env` DB settings (see existing `.env` for defaults). Run migrations:

```bash
php artisan migrate
```

6. Optionally seed users (if seeders exist):

```bash
php artisan db:seed
```

7. Run the application:

```bash
php artisan serve --host=127.0.0.1 --port=8000
```

Notes:
- The included `.env` in the project uses `APP_URL=http://news-portal.test/` and Mailtrap SMTP settings for development. Update these values for your environment.

## Database & Seeders

- This project contains migrations in `database/migrations`.
- If you want the example admin/user/writer accounts available in the README added to the database, I can create seeders that:
	- create users with the specified emails and passwords (hashed),
	- create roles (admin, writer, user) and assign them appropriately.

## Credentials (included as requested)

Admin Logins:
url:{your host}/admin/login
email: admin@gmail.com
password: password

User Logins:
email: user123@gmail.com
password: 12345678

Writer Logins:
url:{your host}/admin/login
email: writer@gmail.com
password: 12345678

---

## Next steps I can take for you

- Create seeders to insert the above users and assign roles automatically.
- Run the app locally and verify admin & frontend routes.
- Add CONTRIBUTING.md and LICENSE if you want to publish the repo.

If you'd like me to generate seeders and run them (or commit & push changes), tell me which options you prefer and the host URL to use for the README credentials (or I can leave the placeholder `{your host}`).
