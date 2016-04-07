ORM
===

Требования
----------

* ORM обеспечивает 2 основных процесса: из данных бизнес логики создаем структуру для запроса в БД и из ответа БД создаем данные для бизнес логики
* ORM должна осуществлять только маппинг и не делать никаких действий. В том числе не должна делать сами запросы в БД. Работа должна осуществляться через интерфейсы без упоминания конкретных БД или драйверов
* Поддержка рефакторинга. В текстовом виде поля объекта могут упоминаться только внутри класса объекта. То есть любой рефакторинг должен иметь возможность быть сделанным не выходя из файла с классом объекта
* Должна быть поддержка обновления данных конкретного объекта. Если у объекта изменилось поле name, то запрос в MySQL должен быть UPDATE ... SET name = :newName WHERE id = :id

Основные сценарии использования
-------------------------------

* Во всех случаях на выходе мы получаем подготовленную для запроса в БД информацию. 
* Получить данные из БД по заданному фильтру. На входе мы имеем набор фильтров. Каждый фильтр состоит из трех обязательных атрибутов: field, operator, value.
* Сохранить данные в бд. На входе мы имеем объекты.
