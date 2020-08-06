# django-dock
# describe
you can connect to mysql container from python3-alpine container if you follow bellow steps.
and if you want to connect to mysql container from Host then `mysql -u root or dbuser -p 3006`.

# steps
1. docker-compose build
1. docker-compose up -d
1. docker-compose exec app /bin/ash
1. make project `django-admin startproject mysite`
1. cd mysite
1. update a part of database of settings.py
`DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'database',  # 作成したデータベース名
        'USER': 'root',  # ログインユーザー名
        'PASSWORD': 'pass',
        'HOST': 'db',
        'PORT': '3306',
    }
}`
1. python manage.py migrate
1. python manage.py runserver 0.0.0.0:8000
