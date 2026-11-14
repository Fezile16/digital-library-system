# Digital Library and Book Borrowing System

A Django web application that helps a school or community library manage its books, members and loans. It is used by members who borrow books, librarians who run the library, and administrators who manage the system.

**Learner:** Fezile Mtshali · **Student number:** 10217 · **Supervisor:**  MR Jeff (GitHub: osijeff)

## Problem

Many small libraries still record books and loans in paper registers. Books get lost, nobody knows who has which book, overdue loans are not followed up, and finding a book takes a long time. This system moves the whole process online so that books, members, loans and fines are tracked in one secure place.

## Features

- Registration, login, logout and password reset
- Role-based access for members, librarians and administrators
- Book and category management (create, view, update, delete) with total and available copies
- Search and filter books by title, author or category
- Borrowing and returns, with automatic due dates and a check that a copy is available
- Overdue fines calculated from the days overdue
- "My loans" page for members
- Reports (overdue loans, most borrowed books, books on loan, loans per member) with PDF and CSV export
- Deployment on PostgreSQL over HTTPS

## User Roles

| Role | What they can do |
| --- | --- |
| Member | Register, log in, search books, borrow and return books, view their own loans and fines |
| Librarian | Manage books, categories and member records, record loans and returns, view overdue loans and reports |
| Administrator | Manage users, roles and system settings through the Django admin |

## Tech Stack

| Part | Technology |
| --- | --- |
| Language | Python <<version, run `python --version`>> |
| Framework | Django <<version, run `pip show django`>> |
| Database | SQLite (development), PostgreSQL (production) |
| Frontend | Django templates and Bootstrap |
| Reports | ReportLab (PDF), CSV export |
| Deployment | Gunicorn, WhiteNoise, hosted with HTTPS |
| Testing | Django test framework |

## Setup

### Requirements

- Python 3.14.6
- Git
- PostgreSQL (production only; development uses SQLite)
- Django 6.1.1

### Installation

```bash
git clone https://github.com/Fezile16/digital-library-system.git
cd digital-library-system
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
pip install -r requirements.txt
```

### Environment variables

Copy the example file and fill in your own values:

```bash
cp .env.example .env
```

| Variable | Purpose |
| --- | --- |
| `DJANGO_SECRET_KEY` | Django secret key |
| `DJANGO_DEBUG` | `True` for development, `False` for production |
| `DJANGO_ALLOWED_HOSTS` | Comma-separated host names |
| `DB_ENGINE`, `DB_NAME`, `DB_USER`, `DB_PASSWORD`, `DB_HOST`, `DB_PORT` | Database connection |

Never commit `.env`, passwords or secret keys.

### Database and demo data

```bash
python manage.py migrate
python manage.py createsuperuser
```

Add sample categories, books and members through the admin site at http://127.0.0.1:8000/admin.

### Run the application

```bash
python manage.py runserver
```

Open http://127.0.0.1:8000/

## Running the Tests

```bash
python manage.py test
```

## Demo Accounts

Create demo accounts for each role (member, librarian, administrator) in the admin site. Ask your supervisor for the login details; do not publish passwords in this file.

## Project Documents

| Document | Location |
| --- | --- |
| Proposal | `docs/` |
| Requirements (SRS) | `docs/` |
| Work Breakdown Structure | `docs/` |
| Design (ERD, URL map, wireframes) | `docs/` |
| Test plan | `docs/` |

## Screenshots

[Add screenshots of the main pages here.]