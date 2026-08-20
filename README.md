# LaraOffers

Laravel app for browsing store offers and coupons with likes, comments, view counts, and image uploads. Personal study project.

## Features

- Browse offers filtered by tags and keyword search
- View offer details with comments, likes, and view tracking
- Browse and manage stores
- Create and manage coupons with expiration dates
- Upload images for offers and stores
- Register, log in, and manage your content from a dashboard
- Database seeder with sample offers, stores, coupons, and users

## Tech stack

- **Runtime:** PHP 8, Laravel 9
- **Views:** Blade components, Tailwind CSS, Alpine.js
- **Database:** MySQL via Eloquent
- **Uploads:** Image files stored in `storage/app/public`
- **Dev tools:** Laravel Pint, Clockwork

See [composer.json](./composer.json) and [package.json](./package.json) for full dependency lists.

## Requirements

- [PHP](https://www.php.net/) >= 8.0.2 with required extensions
- [Composer](https://getcomposer.org/)
- [Git](https://git-scm.com/)
- [MySQL](https://www.mysql.com/) (or change the driver in `config/database.php`)

## Environment variables

Copy `.env.example` to `.env` and fill in the values below.

| Variable | Required | Default |
| --- | --- | --- |
| `DB_DATABASE` | Yes | `laravel_offers` |
| `DB_USERNAME` | Yes | `root` |
| `DB_PASSWORD` | Yes | — |

All other variables use sensible Laravel defaults for local development.

## Getting started

```bash
git clone https://github.com/brunopas/laravel-offers.git
cd laravel-offers

composer install
cp .env.example .env
php artisan key:generate
```

Create a MySQL database called `laravel_offers` (or whatever you set in `DB_DATABASE`), then:

```bash
php artisan migrate --seed
php artisan storage:link
php artisan serve
```

Open [http://localhost:8000](http://localhost:8000).

## Project structure

```text
laravel-offers/
├── app/
│   ├── Http/Controllers/   # Offer, Coupon, Store, User, OfferComment, OfferLike
│   └── Models/              # User, Offer, Coupon, Store, OfferComment, OfferLike, OfferView
├── config/                  # Laravel config files
├── database/
│   ├── factories/           # Model factories for seeding
│   ├── migrations/          # Schema migrations
│   └── seeders/             # DatabaseSeeder
├── public/                  # Static assets, images, Tailwind CSS
├── resources/views/         # Blade templates (offers, coupons, stores, users)
├── routes/                  # web.php
└── tests/                   # PHPUnit tests
```

## License

MIT. See [LICENSE](./LICENSE).
