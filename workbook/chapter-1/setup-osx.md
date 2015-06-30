## Exercise 1.1 - Setup for OSX

The gist of this exercise is to check the dependencies by executing these commands. If all result in some version number, you are ready for this workshop. Otherwise, jump to the first section below:

```bash
$ python --version
$ pip --version
$ virtualenv --version
$ git --version
```


### A. Python 2.7 or 3.4

OSX Mavericks and Yosemite come with a built-in Python 2.7.x. No need to worry about installing a new one. 

#### 1. Check if Python is installed or accessible. Open the Terminal. Most likely, you have Python installed:

```bash
$ python --version
```

#### 2. On Yosemite, you should see:

```bash
Python 2.7.x
```

#### 3. Unless absolutely necessary, you want to install manually, use [Homebrew](http://brew.sh/) (optional).

```bash
$ brew install python
```

#### 4. Check again if Python is installed:

```bash		
$ python --version
```

#### 5. If all goes well, you should see:

```bash
Python 2.7.x
```

### B. Pip

If you have installed Python via Homebrew, its installer already is bundled with Setuptools and Pip.

#### 1. Check if Pip is installed. Open the Terminal and execute:

```bash
$ pip --version
```

#### 2. If this is what you see, then you don’t have Pip installed:

```bash		
-bash: pip: command not found
```

#### 3. Install Pip by downloading this script ([https://bootstrap.pypa.io/get-pip.py](https://bootstrap.pypa.io/get-pip.py)) and executing this line in the Terminal:

```bash		
$ python get-pip.py
```

#### 4. Check again if Pip is installed. Open the Terminal and execute:

```bash		
$ pip --version
```

#### 5. If all goes well, you should see:

```bash
pip 1.5.x
```


### C. VirtualEnv

#### 1. Install VirtualEnv. Open the Command Prompt and execute:

```bash
$ sudo pip install virtualenv
```

#### 2. Check if VirtualEnv is already installed. Reopen the Command Prompt and execute:

```bash
$ virtualenv --version
```

#### 3. If all goes well, you should see

```bash
virtualenv 1.x.x
```

### D. Git (optional)

As a developer, there's no excuse not to use Git. But if you don't have it in your machine, you don't have to worry about it. It's not really part of Django. Also, it's impractical to install its prerequisite - the Xcode Command Line Tools which has quite a large installer.

Download the installer here ([http://git-scm.com/download/mac](http://git-scm.com/download/mac)).