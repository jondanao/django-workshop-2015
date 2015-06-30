## Exercise 1.2 - Setup for Linux

The gist of this exercise is to check the dependencies by executing these commands. If all result in some version number, you are ready for this workshop. Otherwise, jump to the first section below:

```bash
$ python --version
$ pip --version
$ virtualenv --version
$ git --version
```


### A. Python 2.7 or 3.4

The latest Ubuntu and Fedora come with a built-in Python 2.7.x. No need to worry about installing a new one. 

#### 1. Check if Python is installed or accessible. Open the Terminal. Most likely, you have Python installed:

```bash
$ python --version
```

#### 2. You should see:

```bash
Python 2.7.x
```


### B. Pip

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

As a developer, there's no excuse not to use Git. But if you don't have it in your machine, you don't have to worry about it. It's not really part of Django.

**On Fedora**

```bash
$ sudo yum install git
```
**On Debian / Ubuntu**

```bash
$ sudo apt-get install git
```



