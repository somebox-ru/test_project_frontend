# Тестовый проект для Vue-разработчика

Привет! Круто, что ты решил присоединиться к нашей команде. Меня зовут Александр, я собираю команду крутых разработчиков(или тех, кто ими хочет стать). Вместе мы решаем сложные задачи. Мы делаем проекты для собственных нужд, а значит - твоя работа позволяет развиваться компании

Сейчас я расскажу тебе как всё устроено у нас в команде в плане разработки, а затем расскажу что нужно сделать, чтобы к нам попасть.

## Процесс разработки

Коммуникацию с тобой будет держать проект-менеджер. ПМ обычно ставит задачи в таск-трекере. В целом процесс состоит из простых этапов:
- **Постановка задачи** (ПМ описывает задачу и ставит вас исполнителем)
- **Примерная оценка** (ожидаем от тебя уточнения по задаче - ты должен четко понимать что нужно будет сделать и как это сделать, и примерную оцену - это нужно для утверждения эстимейтов и бюджета с заказчиком и планирования загруза)
- **Утверждение** (ПМ утверждает затраты по задачам и подтверждает задачу в план или просит уточнения)
- **Планирование** (ПМ ставит задачу в план, можно приступать к её реализации)
- **Решение задачи** (тут ожидаем от тебя красивого решения задачи. Если нужна помощь или возник вопрос/переоценка/что-угодно другое - сообщи ПМ. Мы за открытость, а поскольку команда удаленная нам важна коммуникация в первую очередь)
- **Задача решена** (ты выгружаешь решение на тестовое окружение, меняешь статус по задаче, задача переходит в тестирование в первую очередь к ПМ и/или на code-review к ответственным лицам)
- **Подтверждение ответственными лицами** (ПМ или тим-лид подтверждает решение и дает добро на выгрузку в продакшен. Некоторые проекты мы не можем выгружать в определенное время(высокая нагрузка/зависимость от других задач), поэтому ПМ может согласовать выгрузку в определенную дату. Обычно выгрузка - это merge ветки задачи/тестового окружение в продакшен)

### Про окружение и CI/CD
На всех проектах мы имеем тестовое окружение, где другие участники процесса могут проверить результаты работы команды. Мы также следуем концепции CI/CD, делая всё, чтобы ребята могли выгружать код используя только гит. Если что-то будет необходимо сделать с сервером до/после выгрузки - сообщи об этом ПМ, он решит этот вопрос или любой другой.

### Про эстимейты и декомпозицию
Стуктурирование очень важно при работе со сложными/комплексными задачами. Поэтому мы просим раскладывать все задачи на отрезки длиной от 15 минут до 2 часов. Если задача занимает 2+ часов, то она должна быть декомпозирована на более мелкие. Задачи длиной меньше 15 минут в нашей вселенной быть не может :)

### Про коммуникации
Поскольку у нас удаленка, нам очень важна коммуникация и прозрачность процессов. И тут нельзя не сказать о важности ПМ - очень важный человек, строй с ним хорошую коммуникацию. 
Кроме того у нас есть некоторые ежедневные процессы, которых просим придерживаться:

- **Daily** (каждый день коммуникация с ПМ и командой по 10-20 минут для синхронизации по задачам)
- **Ежедневный чек по задачам и затраченному времени** (каждый вечер просим потратить время на то, чтобы отписаться по задачам, которые были взяты в работу и выполнены или не доделаны - сколько затратил времени, что осталось доделать. Также просим запушить в гит результат своей работы каждый день, даже если работа еще не закончена - создать отдельную ветку под каждую задачу -- **это единственный элемент контроля твоей работы, который мы требуем**. Если день был не очень продуктивный или что-то пошло не так - сообщи об этом ПМ. Мы лояльны и открыты, нам важно, чтобы работа шла и была прозрачна)

Поскольку у нас удаленка и свобода в приоритете, то мы ожидаем, что ты будешь на связи с 9-00 до 18-00 по МСК. Когда ты будешь решать задачи - выбираешь ты. Мы просим:
- постараться попадать в свои же оценки
- быть доступным для коммуникаций в рабочее время(либо предупреждать ПМа если куда-то нужно отойти, всякое бывает)
- быть честным, открытым, активным и позитивным ;)

# Тестовое задание

Мы не сторонники интервью и сложных тестовых на часы. Предлагаем выполнить простые задачки в рамках имеющегося проекта. Проверять их будем двумя путями:
- тесты
- просмотр кода

## Содержание задания
Необходимо сформировать страницу редактирования карточки товара. 

Для этого через POST запрос к https://api-dev.shop-delivery.ru/int_api/ozon/v3/category/attribute с параметрами:
```
{
  "attribute_type": "ALL",
  "category_id": [
  17034410
  ],
  "language": "DEFAULT"
}
```
На основании полученных данных необходимо построить форму редактирования карточки товара.
В структуре данных поля: 
- **is_required** - признак обязательного поля
- **is_dictionary** - признак словарного поля.

Если поле словарное - то получить перечень доступных вариантов можно через метод: 
https://api-dev.shop-delivery.ru/int_api/ozon/v2/category/attribute/values

Формат запроса:
```
{
  "attribute_id": 10096,
  "category_id": 17028968,
  "language": "DEFAULT",
  "last_value_id": 0,
  "limit": 20,
  "query": ""
}
```
где: 
- **attribute_id** - Идентификатор характеристики
- **category_id** - Идентификатор категории (берем из предыдущего запроса)
- **query** - строка для поиска (используется для автоподстановки)
Если значений 20 и больше - реализовать автокомплит по вводу.

После заполенния полей, кнопка сохранить должна сгенерировать произвольный JSON с заполненными данными. Вывести его в поле textarea внизу страницы. Формат JSON произвольный. 
Так же на основании данного JSON должна быть возможность обратно заполнить поля карточки
Схематичное изображение интерфейса который должен получиться
![image](https://user-images.githubusercontent.com/5597167/160125582-a37e1dd2-ef70-4eef-8583-59c9be45688c.png)

## Сдача проекта
Проект должен быть выполнен на Vue.JS. Предоставлять в виде архива менеджеру, который предоставил ссылку на репозиторий. 
