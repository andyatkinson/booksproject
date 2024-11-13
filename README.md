# booksproject project 

## books app
Models: Authors, Publishers, and Books

## Dev
Using Fish shell:
```sh
source myenv/bin/activate.fish
```

## Install dependencies
```sh
pyenv global
```
```sh
poetry install
```

## Postgres
Uses a custom schema `booksapp`, user `booksapp`, and local database is `books_dev`.

```
DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": "books_dev",
        "USER": "booksapp",
        "PASSWORD": "booksapp",
        "HOST": "localhost",
        "PORT": 5432,
        "OPTIONS": {"options": "-c search_path=booksapp,public"},
    }
}
```

## Migrate
```sh
python manage.py migrate
```

## Usage
```python
python manage.py shell
```
```python
from books.models import Author, Publisher, Book
Author.objects.create(first_name="Andrew",last_name="Atkinson")
<Author: Author object (1)>
author=Author.objects.first()
author.__dict__
```
