# Setting up the project locally

1. Pre-requisites:

   - PostgreSQL (https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)
   - Docker (https://desktop.docker.com/win/stable/Docker%20Desktop%20Installer.exe)
   - Python (https://www.python.org/downloads/release/python-386/)
   - Redis (https://redislabs.com/blog/redis-on-windows-10/)
   - Git (https://git-scm.com/download/win)

2. Clone this repository using the command:
   `$ git clone https://github.com/VirangParekh/p-Indicator.git`

3. Create database using the command:
   `$ createdb -U postgres pindicator --password <password_for_superuser>`

4. Setup virtual environment by doing:
   `$ python -m venv env` and activate using:
   `$ .\env\Scripts\activate` (on Windows)

5. Install requirements using:
   `$ pip install -r requirements/local.txt`,
   `$ pip install -r requirements/base.txt` and
   `$ pip install -r requirements/production.txt`

6. Set the environment varibles as:

   - `$ SET DATABASE_URL=postgres://postgres:<password_for_superuser>@127.0.0.1:5432/pindicator`
   - `$ SET CELERY_BROKER_URL=redis://localhost:6379/0`
   - `$ SET USE_DOCKER=no` (docker not yet setup)

7. Run mingrations:
   `$ python manage.py migrate` and run the server using `$ python manage.py runserver`

Project runs at https://127.0.0.1:8000
