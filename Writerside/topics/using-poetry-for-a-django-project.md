# Using poetry for a Django project     





Assuming you're in your newly created repo then you begin with
```shell
poetry init
```


poetry add Django

poetry add djangorestframework

poetry config virtualenvs.in-project true

poetry update to install the added packages

poetry run django-admin startproject bookstore .