## Exercise 2.2 - Creating the Django Project

#### 1. Start a Django project in the project directory

```bash
# On OSX or Linux
(venv)website.com $ django-admin.py startproject project .
```

```bash
# On Windows
(venv)website.com $ python -m django-admin startproject project .
```

#### 2. Run the site server and browse the site

```bash
(venv)website.com $ python manage.py runserver
```

If everything goes well, you should see this:

![](it-worked.png)


#### 3. Convert project folder to a Git repo

```bash
(venv)website.com $ git init .
```

#### 4. Create and edit `.gitignore` file.

```gitignore
*.pyc
venv
```


#### 5. Stage all files and commit!

```bash
(venv)website.com $ git add .
(venv)website.com $ git commit -m "Created a Django project"
```

#### 6. Verify your last commit. It should say `nothing to commit`.

```bash
(venv)website.com $ git status
```

#### Challenge: Feeling Advanced? You look advanced. You can do this!

> Why don’t you try streamlining your project using GitFlow or Feature Branch Workflows? They say these workflows are great especially if you’re working with a team.
