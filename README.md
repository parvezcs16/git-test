<p align="center"><img src="https://github.com/parvezcs16/internship/blob/main/image.png" width="200"></p>

<h1 align="center"><i>AI</i>FLO - by <i>AI</i>Factor</h1>

## Current Version:

- **AIFLO 0.2.24**

## Table of Contents

- [Installation](#installation)
- [Setting Up Environment Variables](#setting-up-environment-variables)
- [Setting Up Database](#setting-up-database)
- [Starting the Backend Server](#starting-the-backend-server)
- [Users Registration](#users-registration)
- [Screenshots](#screenshots)
- [API Documentation](#api-documentation)
- [Application Requirements](#application-requirements)

---

## Installation

### For Linux

#### 1. Installing Anaconda (Version 2023.09-0)

<p align="center">
<a href="https://www.anaconda.com/" target="_blank">
    <img alt="Anaconda" src="https://img.shields.io/badge/Anaconda-2023.09-42B029?style=for-the-badge&logo=anaconda">
  </a>
</p>

Download and install Anaconda with the following commands:

```bash
curl -O https://repo.anaconda.com/archive/Anaconda3-2023.09-0-Linux-x86_64.sh
bash ~/Downloads/Anaconda3-2023.09-0-Linux-x86_64.sh
```

Follow the prompts:

Press Enter to review the license, and type yes to agree.
Accept the default installation path by pressing Enter.
To initialize Anaconda, use conda init.


## Installing Redis
<p align="center">
  <a href="https://redis.io/" target="_blank">
    <img alt="Redis" src="https://img.shields.io/badge/Redis-v7.2-red?style=for-the-badge&logo=redis">
  </a>
</p>
To install and secure Redis on Ubuntu 20.04 or latest, follow these steps:

1. Install Redis

Update your package list and install Redis:
```bash
sudo apt update
sudo apt install redis-server
```

2. Configure Redis
Open the Redis configuration file:

```bash
sudo nano /etc/redis/redis.conf
```
Change the `supervised` directive to `systemd`:

```
supervised systemd
```
Save and close the file.

3. Restart Redis
Restart Redis to apply the configuration changes:

```bash
sudo systemctl restart redis-server
```
Enable Redis to start on boot:

```bash
sudo systemctl enable redis-server
```
4. Test Redis
Check if Redis is working and secure by connecting with the Redis CLI:

```bash
redis-cli
```
Run a simple command to test:
```bash
ping
```
You should receive `PONG` as a response.


#### 3. Installing PostgreSQL and Set Up Database

<p align="center">
  <a href="https://www.postgresql.org/" target="_blank">
    <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-v14-blue?style=for-the-badge&logo=postgresql">
  </a>
</p>
Install PostgreSQL:

```

sudo apt install postgresql

```

Login to PostgreSQL:

```
sudo su - postgres

postgres@user-dy5xxx:~$ psql

```

In the PostgreSQL shell, create a role and databases:

```

postgres=# create role <role-name> with login password '<your-password>';
postgres=# create database <database-name> owner '<role-name>';
postgres=# create database <test-database-name> owner '<role-name>';

```

4. Install Required Packages Using Conda
   For Linux:

```

conda env create -f env-linux.yml

```

For Windows:

```

conda env create -f env-win.yml

```

### Activate the Environment:

For most shells (bash, zsh, etc.):

```bash
conda activate aiflo
```
Or, with `source` if `conda activate` doesn’t work:

```bash
source activate aiflo
### Explanation:
- **`conda activate aiflo`** is the standard command used for most modern shells.
- **`source activate aiflo`** is an older method that can still be used if someone encounters issues with the standard method, especially in certain setups.

Both options are useful to cover all cases.
```

Setting Up Environment Variables
Create a .env file in the aiflo-api directory.

Add the following variables to the .env file:

```

FLASK_APP=aifapi
FLASK_ENV=development
AIF_USERNAME='<role-name>'
AIF_PASSWORD='<your-password>'
AIF_HOSTNAME='localhost'
AIF_PORT='5432'
AIF_DBNAME='<database-name>'
AIF_TEST_DBNAME='<test-database-name>'

```

Setting Up Database
Navigate to the aiflo-api directory:

```

cd aiflo-api

```

Activate the environment:

```

conda activate aiflo

```

Initialize and migrate the database:

```

flask db init
flask db migrate
flask db upgrade

```

Starting the Backend Server
Navigate to the aiflo-api directory:

```

cd aiflo-api

```

Activate the environment:

```

conda activate aiflo

```

Start the Flask server:

```

flask run

```

## Users Registration

1. Run the frontend `yarn` server.
2. Open the user registration page.
3. Enter the required information.
4. Verify your email.
5. Login and start using AIFLO.

---

## Screenshots

Include any screenshots of your application here.

---

## API Documentation

Provide a link to or description of your API documentation.

---

## Application Requirements

- **Anaconda** 2023.09
- **Python** 3.x
- **PostgreSQL** 14+
- **Flask** 2.x
- Conda environment files (`env-linux.yml`, `env-win.yml`)
