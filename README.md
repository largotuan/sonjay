![Saleor Commerce - A GraphQL-first platform for perfectionists](https://user-images.githubusercontent.com/249912/71523206-4e45f800-28c8-11ea-84ba-345a9bfc998a.png)

<div align="center">
  <h1>Saleor Commerce</h1>
</div>

<div align="center">
  <strong>Customer-centric e-commerce on a modern stack</strong>
</div>

<div align="center">
  A headless, GraphQL-first e-commerce platform delivering ultra-fast, dynamic, personalized shopping experiences. Beautiful online stores, anywhere, on any device.
</div>

<br>


   [![Build Status](https://travis-ci.org/simkimsia/UtilityBehaviors.png)](https://travis-ci.com/gitlab/sonnhfit/sonjay)


## Table of Contents

- [What makes Saleor special?](#what-makes-saleor-special)
- [Features](#features)
- [Installation](#installation)
- [Documentation](#documentation)
- [Demo](#demo)
- [Contributing](#contributing)
- [Translations](#translations)
- [Your feedback](#your-feedback)
- [License](#license)


Saleor is free and always will be.
Help us out… If you love free stuff and great software, give us a star! 🌟

![Saleor Storefront - React-based PWA e-commerce storefront](https://user-images.githubusercontent.com/249912/71527146-5b6be280-28da-11ea-901d-eb76161a6bfb.png)
![Saleor Dashboard - Modern UI for managing your e-commerce](https://user-images.githubusercontent.com/249912/71523261-8a795880-28c8-11ea-98c0-6281ea37f412.png)

## Installation

Saleor requires Python 3.8, Node.js 10.0+, PostgreSQL and OS-specific dependency tools.

## build

```
docker-compose build
```

## run

```
docker-compose up -d
```

## migration

```
docker-compose run --rm api python3 manage.py migrate
docker-compose run --rm api python3 manage.py collectstatic --noinput
```


## create sample db

```
docker-compose run --rm api python3 manage.py populatedb
```

## create supseruser

```
docker-compose run --rm api python3 manage.py createsuperuser
```

### install precommit

```
pip install pre-commit # or
pip3 install pre-commit
```

### autotest run local
```
    docker-compose build
    docker-compose run api python manage.py collectstatic --noinput --verbosity=0
    docker-compose run api black --check .
    docker-compose run api flake8 saleor
    docker-compose run api isort --check-only saleor
    docker-compose run api sh -c 'find saleor -name "*.py" -type f ! -path "*tests*" | xargs pydocstyle -v'
    docker-compose run api python manage.py migrate
    docker-compose run api python manage.py makemigrations --dry-run --check
    docker-compose run api pytest --cov --cov-report= --django-db-bench="/tmp/queries-results.json"
```
