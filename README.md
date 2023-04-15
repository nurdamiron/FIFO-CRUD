# FIFO-CRUD
### Для решения вашей задачи предлагается следующий алгоритм и реализация REST API:

#### Создайте две таблицы в вашей базе данных (supply и sale), как указано в задании.

### Реализуйте следующие REST API методы:
  - Создание, редактирование, удаление и просмотр закупа. 
      POST /supplies
      Создает новую закупку.
      Пример тела запроса:
      
      {
        "barcode": "123456",
        "quantity": 10,
        "price": 100,
        "time": "2023-04-15T14:00:00"
      }

PUT /supplies/{id}
Редактирует существующую закупку.
Пример тела запроса:
{
"quantity": 5,
"price": 150,
"time": "2023-04-15T15:00:00"
}

DELETE /supplies/{id}
Удаляет существующую закупку.

GET /supplies/{id}
Возвращает информацию о существующей закупке.

ii. Создание, редактирование, удаление и просмотр продажи.

POST /sales
Создает новую продажу.
Пример тела запроса:
{
"barcode": "123456",
"quantity": 2,
"price": 200,
"time": "2023-04-15T16:00:00"
}

PUT /sales/{id}
Редактирует существующую продажу.
Пример тела запроса:
{
"quantity": 3,
"price": 250,
"time": "2023-04-15T17:00:00"
}

DELETE /sales/{id}
Удаляет существующую продажу.

GET /sales/{id}
Возвращает информацию о существующей продаже.

iii. Подсчет прибыли за период с учетом себестоимости по FIFO.

GET /profit?start_date=2023-04-01&end_date=2023-04-30
Возвращает прибыль за указанный период с учетом себестоимости по FIFO.
Реализуйте логику подсчета прибыли по FIFO. При создании, редактировании или удалении продажи или закупки, сначала отсортируйте записи по времени, затем для каждой продажи найдите соответствующие закупки и рассчитайте себестоимость с учетом FIFO. Наконец, вычислите общую прибыль за заданный период.
