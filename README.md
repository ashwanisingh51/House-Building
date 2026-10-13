# House Building: Full-Stack Construction Company Website

A full-stack website for a house-building company. Visitors can browse services, projects, the team and testimonials, and send an enquiry. Admins sign in to manage products and read the enquiries and registered users.

**Stack:** React, Node.js, Express, MongoDB (Mongoose), JWT, bcrypt

## Features

- Public pages: Home, About, Services, Projects, Team, Testimonials, Blog, Contact
- Contact form that saves enquiries to the database
- Sign up and log in with hashed passwords (bcrypt) and JWT tokens
- Two roles, `user` and `admin`
- Admin panel with tables of users and contact enquiries
- Product management API with image upload (create, read, update, delete)

## Screenshots

The `Screenshots/` folder has images of the public pages (`c*.png`) and the admin views (`p*.png`).

## API overview

| Area | Endpoints |
|---|---|
| Users | `POST /user/signUp`, `POST /user/logIn`, `GET /user/myProfile` (token needed), `PUT /user/update/:id`, `DELETE /user/dataDelete/:id` |
| Products | `POST /product/productCreate`, `GET /product/getAllproduct`, `GET /product/findOneProductByParams/:id`, `PUT /product/update/:id`, `DELETE /product/delete/:id` |
| Contact | `POST /contact/contactCreate`, `GET /contact/getAllContactDetails`, `DELETE /contact/contactDelete/:id` |

## Project structure

```text
House-Building/
├── Backend/         # Express API, Mongoose models, JWT middleware, image upload
├── Setup/           # React frontend (pages, components, auth context)
└── Screenshots/
```

## Run locally

You need Node.js and a MongoDB database (a free MongoDB Atlas cluster works).

1. Backend: create `Backend/.env` with your own values, then start the server.

```text
Server=5000
MongoURL=<your MongoDB connection string>
secretKey=<a long random string>
```

```bash
cd Backend
npm install
npm start
```

2. Frontend:

```bash
cd Setup
npm install
npm start
```

`.env` is listed in `.gitignore` and must never be committed.

## What I would improve

- Add input validation and rate limiting on the auth routes
- Protect the product and contact admin routes with the admin role check
- Move the frontend into a `frontend/` folder and add tests
