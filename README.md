[![Java CI with Gradle](https://github.com/KleoVor/PatternsDateChange/actions/workflows/gradle.yml/badge.svg)](https://github.com/KleoVor/PatternsDateChange/actions/workflows/gradle.yml)

# Задача №1: заказ доставки карты (изменение даты)
Вам необходимо автоматизировать тестирование новой функции формы заказа доставки карты:
![image](https://github.com/KleoVor/PatternsDateChange/assets/121848826/227c730e-66ea-4633-bb1b-43ca038bdcc1)

Требования к содержимому полей, сообщения и другие элементы, по словам заказчика и разработчиков, такие же, они ничего не меняли.
Примечание: личный совет — не забудьте это перепроверить, никому нельзя доверять 😈
Тестируемая функциональность: если заполнить форму повторно теми же данными, за исключением «Даты встречи», то система предложит перепланировать время встречи:

![image](https://github.com/KleoVor/PatternsDateChange/assets/121848826/463f1add-2dae-46df-a9bf-0eb67b56670c)

После нажатия кнопки «Перепланировать» произойдёт перепланирование встречи:

![image](https://github.com/KleoVor/PatternsDateChange/assets/121848826/0c39a4b8-cd72-4445-bf49-333074e994fb)

Важно: в этот раз вы не должны хардкодить данные прямо в тест. Используйте Faker, Lombok, data-классы для группировки нужных полей и утилитный класс-генератор данных — см. пример в презентации.
Утилитными называют классы, у которых приватный конструктор и статичные методы.
Обратите внимание, что Faker может генерировать не совсем в нужном для вас формате.


# Задача №2: тестовый режим
Разработчики интернет-банка, изрядно поворчав, предоставили вам тестовый режим запуска целевого сервиса, в котором открыта программная возможность создания клиентов банка, чтобы вы могли протестировать хотя бы функцию входа.
Важно: ваша задача заключается в том, чтобы протестировать функцию входа через веб-интерфейс с использованием Selenide.
Для удобства вам предоставили документацию, которая описывает возможность программного создания клиентов банка через API. Вот дословно представленное ими описание:
Для создания клиента нужно делать запрос вида:

POST /api/system/users
Content-Type: application/json

{
    "login": "vasya",
    "password": "password",
    "status": "active" 
}

Возможные значения поля «Статус»:
* «active» — пользователь активен,
* «blocked» — пользователь заблокирован.

В случае успешного создания пользователя возвращается код 200.
При повторной передаче пользователя с таким же логином будет выполнена перезапись данных пользователя.
Вам нужно самостоятельно изучить реакцию приложения на различные комбинации случаев, для этого придётся вспомнить комбинаторику:\
* наличие пользователя;\
* статус пользователя;\
* невалидный логин;\
* невалидный пароль.

Дополнительно: оцените время, которое вы затратили на автоматизацию, и время, за которое вы проверили бы те же сценарии вручную, используя для тестирования интерфейса браузер и Postman для доступа к открытому API.

Приложите к решению задачи в формате:\
время, затраченное на ручное тестирование (минут): x;\
время, затраченное на автоматизацию (минут): y.
