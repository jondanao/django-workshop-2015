## Exercise 2.3 - Configuring the Site Settings

#### 1. Organize our site by creating necessary folders.

```bash
(venv)website.com $ mkdir apps media static templates
```

#### 2. Edit `/project/settings.py`

```python
TEMPLATES = [
    {
        ...
        'DIRS': [os.path.join(BASE_DIR, 'templates')],
        ...
    },
]

# Static files (CSS, JavaScript, Images)
STATIC_URL = '/static/'
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'static')]

MEDIA_URL = '/media/'
MEDIA_ROOT = 'media'
```

#### 3. Run the server to check that we did not break anything.

```bash
(venv)website.com $ python manage.py runserver
```

#### 4. Apply the initial migration and create super user

```bash
You have unapplied migrations; your app may not work properly until they are applied.
Run 'python manage.py migrate' to apply them.

(venv)website.com $ python manage.py migrate
(venv)website.com $ python manage.py createsuperuser
```

#### 5. Run the server and login to the `/admin/` site.

```bash
(venv)website.com $ python manage.py runserver
```

#### 6. Your project structure should look like this.

```bash
├── apps
├── db.sqlite3
├── manage.py
├── media
├── project
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── requirements.txt
├── static
└── templates
```

#### 7. Stage all files and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Configured the site settings"
```


#### Challenge: Feeling Advanced? You look advanced. You can do this!
> Why don’t you try using **PostgreSQL** as your database instead of SQLite? They say it’s more predictable if you use the same type of database in your dev machine and your production server.
