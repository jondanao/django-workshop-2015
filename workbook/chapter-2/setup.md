## Exercise 2.1 - Setting Up the Development Environment

#### 1. Create the project directory using the terminal and CD into it

```bash
$ mkdir website.com && cd website.com
```

#### 2. Create the virtual environment

```bash
# On OSX or Linux
website.com $ virtualenv venv --no-site-packages
```

```bash
# On Windows, do this if package installations below don’t work
website.com $ virtualenv venv --system-site-packages
```

#### 3. Activate the virtual environment

```bash
# On OSX or Linux
website.com $ source venv/bin/activate
(venv)website.com $
```

```bash
# On Windows
website.com $ venv\Scripts\activate.bat
(venv)website.com $
```

#### 4. Install django

```bash
(venv)website.com $ pip install django
```

#### 5. Save site packages

```bash
(venv)website.com $ pip freeze > requirements.txt
```


#### Challenge: Feeling Advanced? You look advanced. You can do this!
> Why don’t you try **VirtualEnvWrapper**? They say it makes working with virtual environments more pleasant.
