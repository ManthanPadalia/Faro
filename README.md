# Faro

A minimal Airbnb-like listing app built with Node.js, Express, MongoDB, Passport and Mapbox. Features user auth, image uploads via Cloudinary, reviews, geocoding and a small seeded dataset.

## Quick links

- App entry: [app.js](app.js)
- Routes:
  - [routes/listing.js](routes/listing.js)
  - [routes/review.js](routes/review.js)
  - [routes/user.js](routes/user.js)
- Controllers:
  - [`index`](controllers/listing.js) — [controllers/listing.js](controllers/listing.js)
  - [`renderNewForm`](controllers/listing.js) — [controllers/listing.js](controllers/listing.js)
  - [`showListing`](controllers/listing.js) — [controllers/listing.js](controllers/listing.js)
  - [`createListing`](controllers/listing.js) — [controllers/listing.js](controllers/listing.js)
  - [`renderEditForm`](controllers/listing.js) — [controllers/listing.js](controllers/listing.js)
  - [`updateListing`](controllers/listing.js) — [controllers/listing.js](controllers/listing.js)
  - [`destroyListing`](controllers/listing.js) — [controllers/listing.js](controllers/listing.js)
  - [`createReview`](controllers/review.js) — [controllers/review.js](controllers/review.js)
  - [`destroyReview`](controllers/review.js) — [controllers/review.js](controllers/review.js)
  - [`renderSignupForm`](controllers/user.js) — [controllers/user.js](controllers/user.js)
  - [`signup`](controllers/user.js) — [controllers/user.js](controllers/user.js)
  - [`renderLoginForm`](controllers/user.js) — [controllers/user.js](controllers/user.js)
  - [`login`](controllers/user.js) — [controllers/user.js](controllers/user.js)
  - [`logout`](controllers/user.js) — [controllers/user.js](controllers/user.js)
- Models:
  - [models/listing.js](models/listing.js)
  - [models/review.js](models/review.js)
  - [models/user.js](models/user.js)
- Validation / middleware:
  - [schema.js](schema.js)
  - [middleware.js](middleware.js)
  - [utils/ExpressError.js](utils/ExpressError.js)
  - [utils/wrapAsync.js](utils/wrapAsync.js)
- Cloud upload / storage:
  - [cloudConfig.js](cloudConfig.js)
- Frontend assets:
  - [public/js/script.js](public/js/script.js)
  - [public/js/map.js](public/js/map.js)
  - [public/css/style.css](public/css/style.css)
  - [public/css/rating.css](public/css/rating.css)
- Views: layouts and partials in [views/](views/) (main layout: [views/layouts/boilerplate.ejs](views/layouts/boilerplate.ejs))
- DB seed: [init/index.js](init/index.js) / [init/data.js](init/data.js)
- Project metadata: [package.json](package.json)

## Features

- User authentication with Passport and passport-local-mongoose ([models/user.js](models/user.js)).
- Create, read, update, delete listings ([controllers/listing.js](controllers/listing.js), [routes/listing.js](routes/listing.js)).
- Reviews per listing with author checks ([controllers/review.js](controllers/review.js), [routes/review.js](routes/review.js)).
- Image upload to Cloudinary via multer + multer-storage-cloudinary ([cloudConfig.js](cloudConfig.js)).
- Geocoding using Mapbox to attach geometry to listings ([controllers/listing.js](controllers/listing.js) uses Mapbox geocoding).
- Server-side validation with Joi schemas ([schema.js](schema.js)).
- Flash messages, session store using MongoDB ([app.js](app.js)).

## Requirements

- Node.js (matches engines in [package.json](package.json))
- MongoDB (Atlas or local)
- Cloudinary account (for image uploads)
- Mapbox access token

## Environment variables

Create a `.env` with at least:

- ATLASDB_URL — MongoDB connection string (used by [app.js](app.js))
- SECRET — session secret (used by [app.js](app.js))
- MAP_TOKEN — Mapbox token (used by [controllers/listing.js](controllers/listing.js) and [public/js/map.js](public/js/map.js))
- CLOUD_NAME, CLOUD_API_KEY, CLOUD_API_SECRET — Cloudinary credentials (used by [cloudConfig.js](cloudConfig.js))

## Install & run

1. Install dependencies:

```sh
npm install
```
