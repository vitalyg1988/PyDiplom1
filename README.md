# PyDiplom1

Вывести список групп в ВК в которых состоит пользователь, но не состоит никто из его друзей.
В качестве жертвы, на ком тестировать, можно использовать: https://vk.com/eshmargunov

Входные данные:

Имя пользователя или его id в ВК, для которого мы проводим исследование.

Внимание: и имя пользователя (eshmargunov) и id (171691064) - являются валидными входными данными.

Ввод можно организовать любым способом:

    из консоли
    из параметров командной строки при запуске
    из переменной

Выходные данные:

Файл groups.json в формате:

[
    {
    “name”: “Название группы”, 
    “gid”: “идентификатор группы”, 
    “members_count”: количество_участников_сообщества
    },
    {
    …
    }
]

Форматирование не важно, важно чтобы файл был в формате json.

Требования к программе:

    Программа не падает, если один из друзей пользователя помечен как “удалён” или “заблокирован”.
    Показывает что не зависла: рисует точку или чёрточку на каждое обращение к api.
    Не падает, если было слишком много обращений к API (Too many requests per second). Ограничение от ВК: не более 3х обращений к API в секунду.
    Могут помочь модуль time (time.sleep) и конструкция (try/except).
    Код программы удовлетворяет PEP8.
    Не использовать внешние библиотеки (vk, vkapi).

Дополнительные требования (не обязательны для получения диплома):

    Использовать execute для ускорения работы.
    Показывает прогресс: сколько осталось до конца работы (в произвольной форме: сколько обращений к API, сколько минут, сколько друзей или групп осталось обработать).
    Восстанавливается если случился ReadTimeout.
    Показывать в том числе группы, в которых есть общие друзья, но не более, чем N человек, где N задается в коде.

Hint: Если у пользователя больше 1000 групп, можно ограничиться первой тысячей

Hint: Удобно использовать множества
