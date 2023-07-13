# Contact Management System
This contains the [frontend](https://github.com/contact-mgmt-sys/contact-mgmt-sys-fe) and [backend](https://github.com/contact-mgmt-sys/contact-mgmt-sys-be) components.

## Requirements
### Required
* [Python](https://www.python.org/downloads/)
* [PostgreSQL](https://www.postgresql.org/)
* [Node.js](https://nodejs.org/en)
### Optional
* [Git](https://git-scm.com/downloads)

## Setup
### Backend
1. Download and extract the repository or clone it if [git is present](#optional).
```
git clone https://github.com/contact-mgmt-sys/contact-mgmt-sys-be.git
```
2. Install the dependencies.
```
pip install -r requirements.txt
```
3. Create an `.env` file in the root directory and add the following environment variables.
```env
DATABASE_NAME=contact_mgmt_sys
DATABASE_USER=postgres
DATABASE_PASSWORD=postgres
DATABASE_HOST=127.0.0.1
DATABASE_PORT=5432
```
### Frontend
1. Download and extract the repository or clone it if [git is present](#optional).
```
git clone https://github.com/contact-mgmt-sys/contact-mgmt-sys-fe.git
```
2. Install dependencies.
```
npm install
```
3. Create an `.env` file in the root directory and add the following environment variables.
```env
VITE_API_BASE=http://127.0.0.1:8000/
VITE_API_CONTACTS_LIST=http://127.0.0.1:8000/contacts/
VITE_API_CONTACTS_VIEW=http://127.0.0.1:8000/contacts/:id/
```

## Usage
### Backend
1. Migrate the databases.
```
python manage.py migrate
```
2. Start the server.
```
python manage.py runserver
```
### Frontend
1. Start the development server.
```
npm run dev
```

## Docker
### Backend
1. Modify the `.env` file to the following.
```env
DATABASE_NAME=contact_mgmt_sys
DATABASE_USER=postgres
DATABASE_PASSWORD=postgres
DATABASE_HOST=database
DATABASE_PORT=5432
```
2. Build the image and run the container.
```
docker compose up --build
```
### Frontend
1. Modify the `.env` file to the following.
```env
VITE_API_BASE=http://127.0.0.1:8000/
VITE_API_CONTACTS_LIST=http://127.0.0.1:8000/contacts/
VITE_API_CONTACTS_VIEW=http://127.0.0.1:8000/contacts/:id/
```
2. Build the image.
```
docker build -t contact-mgmt-sys-fe .
```
3. Run the container.
```
docker run -p 8080:8080 --name contact-mgmt-sys-fe --env-file .env --rm contact-mgmt-sys-fe
```