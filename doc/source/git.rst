*********************
Папка git
*********************

Клонируем папку с репозитория
=============================

1. Для клонирования репозитория выполните::

    ansible-playbook playbook/git/git_clone.yml -vvv

.. note::
    Что бы не спрашивало пароль выполним следущее::

        git credential-store --file ~/git.store store
        protocol=https
        host=mygithost
        username=bob
        password=s3cre7

Здесь мы просим git-credential-store сохранить некоторые учетные данные: логин “bob” и пароль “s3cre7”, которые будут использоваться при доступе к https://mygithost.

Теперь мы извлечем эти учетные данные. Мы передаем часть уже известных нам параметров подключения (https://mygithost) и пустую строку.

git-credential-store возвращает логин и пароль, которые мы сохранили ранее.

Ниже приведено содержимое файла ~/git.store:

https://bob:s3cre7@mygithost

.. note::
    Ниже приведено содержимое файла ~/git.store::

        https://bob:s3cre7@mygithost