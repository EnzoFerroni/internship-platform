# Sistema de Estágios

[![Java](https://img.shields.io/badge/Java-Spring%20Boot%203.2-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Next.js](https://img.shields.io/badge/Next.js-15-000000?logo=nextdotjs)](https://nextjs.org)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

An internship platform that connects students and companies: job postings, applications, reviews and an admin dashboard.

## Table of Contents

- [About](#about)
- [Features](#features)
- [API](#api)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [License](#license)

## About

A full-stack web application built for a Mackenzie course (2025) with a Spring Boot
REST API, a PostgreSQL database and a Next.js front end. Three kinds of users share
the platform: students, companies and administrators. The UI is in Portuguese.

## Features

- Sign-up and login for students and companies
- Companies publish and manage internship openings
- Students browse openings and apply
- Reviews of companies and internships
- Dashboard with totals and the most popular openings
- Admin area to manage users

## API

| Resource | Base path |
| --- | --- |
| Students | `/estudantes` (CRUD, `/cadastro`, `/login`) |
| Companies | `/empresas` (CRUD, `/cadastro`, `/login`) |
| Openings | `/vagas` |
| Applications | `/inscricoes` (by student or by opening) |
| Reviews | `/avaliacoes` |
| Dashboard | `/dashboard` (`/count`, `/top-vagas`) |
| Admins | `/admins` (CRUD, `/cadastro`, `/login`) |

## Getting Started

Requirements: JDK 17, Maven, Node.js 18+ and a PostgreSQL database.

```bash
git clone https://github.com/EnzoFerroni/sistema-estagios.git
cd sistema-estagios
```

The database connection comes from environment variables:

```bash
export DB_URL=jdbc:postgresql://localhost:5432/estagios
export DB_USERNAME=postgres
export DB_PASSWORD=your_password
```

Then install and start everything:

```bash
chmod +x setup.sh start.sh
./setup.sh   # installs JDK, Maven and Node with apt, then the dependencies
./start.sh   # starts the API on :8080 and the web app on :3000
```

On macOS, skip `setup.sh` and run `mvn spring-boot:run` in `backend/` and
`npm install && npm run dev` in `frontend/`.

## Project Structure

```
├── backend/    Spring Boot API (entities, repositories, controllers)
├── frontend/   Next.js app router (vagas, empresas, estudantes, dashboard...)
├── setup.sh    Dependency installer (Debian/Ubuntu, Codespaces)
└── start.sh    Starts back end and front end together
```

## License

Released under the [MIT License](LICENSE). Copyright (c) 2025 Enzo Ferroni.
