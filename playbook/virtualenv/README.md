https://ru.stackoverflow.com/questions/420040/%D0%9E%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D0%BF%D0%BE%D0%B7%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D1%8F-git-%D0%B1%D0%B5%D0%B7-%D0%B2%D0%B2%D0%BE%D0%B4%D0%B0-%D0%BF%D0%B0%D1%80%D0%BE%D0%BB%D0%B5%D0%B9
Требуется Git версии не ниже 1.7.10
В этом случае вам всегда требуется указывать пароль при общении с сервером. Git можно попросить сохранять на некоторое время (по умолчанию на 15 минут) введённые данные командой:

> git config --global credential.helper cache
При желании можно изменить стандартное время запоминания командой

> git config --global credential.helper "cache --timeout=3600"
(время указывается в секундах)

Вы можете также указать git хранить ваши данные постоянно:

> git config credential.helper store
При этом ваши данные будут храниться в открытом виде в файле .git-credentials.

Обнулить настройки этой возможности можно командой:

> git config --unset credential.helper
При желании можно подобное поведение для всех репозиториев, для этого нужно передать дополнительный ключ --global.

В зависимости от этой настройки, информация с вашими данными будет расположена либо в каталоге проекта, либо в $HOME