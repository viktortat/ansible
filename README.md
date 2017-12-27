# ansible-w
ansible vagrant
# Запускаем виртуальные хосты
1. vagrant up, vagrant status
# Проверяем доступность хостов
2. ansible -m ping all -i hosts/inventory.yml
# Запускаем модуль shell: вводим команду на одном из хостов
3.ansible -i hosts/inventory.yml -m shell -a 'uname -a' 192.168.28.71
# Модуль copy позволяет копировать из управляющей машины на удаленные
4.ansible -i hosts/inventory.yml -m copy -a 'src=/путь/от/куда/ dest=/путь/куда/' 192.168.28.71
# Куча полезных модулей http://docs.ansible.com/ansible/latest/list_of_all_modules.html
# Выбор хостов all означает «все хосты», еще примеры:
- host0.example.org:host1.example.org будет запущен на host0.example.org и на host1.example.org
- host*.example.org будет запущен на всех хостах, названия которых начинается с 'host' и заканчивается на '.example.org'
 (тоже как в shell)
#
