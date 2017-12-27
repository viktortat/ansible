*********************
Папка supervisor
*********************

Установка supervisor
====================

1. Для установки supervisor выполните команду::

    ansible-playbook playbook/supervisor/supervisor_install.yml -vvv

2. Для запуска supervisor::

    ansible-playbook playbook/supervisor/supervisor_start.yml -vvv

3. Для перезапуска supervisor::

    ansible-playbook playbook/supervisor/supervisor_restart.yml -vvv

