
# tzmediasoft тестовое задание на qa 

##1  Написать тест-кейсы на форму авторизации 
Логин от 5 до 20 символов латиницей̆ с учетом регистра. Допустимы цифры. Пароль: от 10 до 20 символов (любые, кроме пробела) с учетом регистра. 
Допустим, что все действия на сайте можно совершить только после авторизации => все тест кейсы с приоритетом Blocker
Тест кейс 1 
Проверка правильной авторизации
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина - test@mail.ru
3.  ввести в поле пароля - Test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: 200 ок, авторизация успешна

Тест кейс 2 
Проверка валидности логина
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина   - ?.!№&__#$@mail.ru  // где «__» - пробел (включая след проверки)
3.  ввести пароль -  Test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: ошибка 401 + сообщение на клиенте «неверный логин» или «логин содержит недопустимые символы»

Тест кейс 3 
Проверка  валидности пароля
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина - test@mail.ru
3.  ввести в поле пароля - Test____21
4. Авторизоваться с помощью enter
Ожидаемый результат: 401 + сообщение на клиенте «пароль включает недопустимые символы»

Тест кейс 4 
Проверка валидности логина без «@» 
1.  зайти на сайт 
2.  ввести в поле логина -  «Test.mail.ru»  
3.  ввести пароль - Test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: ошибка 401 + сообщение на клиенте «логин должен содержать @ »

 
Тест кейс 5 
Проверка пустого поля пароль
1.  зайти на сайт 
2.  ввести в поле логина  - «test@mail.ru»  
3. Авторизоваться с помощью enter
Ожидаемый результат: сообщение на клиенте «введите пароль»

Тест кейс 6 
Проверка пустого поля логин
Шаги:
1.  зайти на сайт 
2.  ввести в поле пароля - Test1233211
3. Авторизоваться с помощью enter
Ожидаемый результат: сообщение на клиенте «введите логин»


Тест кейс 7
Проверка пустых полей
Шаги:
1.  зайти на сайт 
2. Авторизоваться с помощью enter
Ожидаемый результат: сообщение на клиенте «введите логин» и «введите пароль»

Тест кейс 8
Проверка старого пароля (если недавно меняли)
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина - test@mail.ru
3.  ввести в поле пароля- Test123 11111121
4. Авторизоваться с помощью enter
Ожидаемый результат: 401 + сообщение на клиенте «неверный пароль»

Тест кейс 9 
Проверка неверным паролем
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина - test@mail.ru
3.  ввести в поле пароля - Password121212121212 
4. Авторизоваться с помощью enter
Ожидаемый результат: 401 + сообщение на клиенте «неверный пароль»


Тест кейс 10 
Проверка перемещения табуляцией
Шаги:
1.  зайти на сайт 
2.  Переместиться с помощью tab в поля логин, пароль, кнопки авторизации
Ожидаемый результат: текстовый курсор перемещается

Тест кейс 11 
Проверка отсутствия логина в url, а в куках пароля, после успешной авторизации 
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина - test@mail.ru
3.  ввести в поле пароля - Test1233211
4. Авторизоваться с помощью enter
5. Devtools -   смотрим в url наличие логина 
6. Devtools – в куках смотрим нет ли пароля
Ожидаемый результат: данные не передаются

Тест кейс 12 
Проверка опции вкл «запомнить меня» 
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина - test@mail.ru
3.  ввести в поле пароля - Test1233211
4. Поставить чекбокс «запомнить меня»
5. Авторизоваться с помощью enter
6. Закрыть браузер 
7. Открыть браузер и зайти на сайт 
Ожидаемый результат: пользователь попадает на сайт авторизованным

Тест кейс 13 
Проверка опции откл  «запомнить меня»
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина - test@mail.ru
3.  ввести в поле пароля - Test1233211
4. Авторизоваться с помощью enter
6. Закрыть браузер 
7. Открыть браузер и зайти на сайт 
Ожидаемый результат: пользователь попадает на форму авторизации


Тест кейс 14 
Проверка логина на валидность > 5
Шаги:
1.  зайти на сайт 
2.  Ввести в поле логина 1@b.r
3.  ввести в поле пароля - Test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: сообщение на клиенте «логин слишком короткий»

 
Тест кейс 15
Проверка логина на валидность < 20 
Шаги:
1.  зайти на сайт 
2.  Ввести в поле логина 1FKFFJFWFKWKFKWFKWFKWFFefwfwf@b.ru
3.  ввести в поле пароля - Test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: сообщение на клиенте «логин слишком длинный»

Тест кейс 16 
Проверка логина на валидность латиницы
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина   - Тест1@mail.ru  
3.  ввести пароль - Test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: ошибка 401 + сообщение на клиенте «неверный логин» или «логин содержит недопустимые символы»

Тест кейс 17 
Проверка валидности логина по верхнему регистру 
Предисловие: в документации должно быть сказано, что при регистрации клиент должен использовать заглавные буквы в поле логин 
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина   - test@mail.ru  
3.  ввести пароль - Test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: ошибка 401 + сообщение на клиенте «неверный логин» или «логин должен содержать заглавные буквы»

Тест кейс 18 
Проверка валидности пароля по верхнему регистру 
Предисловие: в документации должно быть сказано, что при регистрации клиент должен использовать заглавные буквы в поле логин 
Шаги:
1.  зайти на сайт 
2.  ввести в поле логина   - Test@mail.ru  
3.  ввести пароль - test1233211
4. Авторизоваться с помощью enter
Ожидаемый результат: ошибка 401 + сообщение на клиенте «неверный пароль» или «пароль должен содержать заглавные буквы»

 
Тест кейс 19
Проверка пароля на валидность > 10 
Шаги:
1.  зайти на сайт 
2.  Ввести в поле логина Test@mail.ru  
3.  ввести в поле пароля - Test12
4. Авторизоваться с помощью enter
Ожидаемый результат: сообщение на клиенте «пароль слишком короткий»

Тест кейс 20
Проверка пароля на валидность < 20
Шаги:
1.  зайти на сайт 
2.  Ввести в поле логина Test@mail.ru  
3.  ввести в поле пароля - Test12Test12Test12Test12Test12Test12Test12
4. Авторизоваться с помощью enter
Ожидаемый результат: сообщение на клиенте «пароль слишком длинный»




##2 На основе первого задания выявить граничные значения на логин и пароль 
Для логина – 4,5,6 символов нижняя граница и 19,20,21 символов верхняя 
Для пароля – 9,10,11 символов нижняя граница и 19,20,21 символов верхняя

##3 Тест план
Тест-план для мобильного приложения контроля работы водителей-экспедиторов
Цель тестирования:
Удостовериться, что мобильное приложение корректно работает на обеих платформах (Android и iOS), обеспечивая функциональность считывания штрих-кодов, отправку информации в базу данных и привязку пункта доставки к геопозиции устройства.
Основные функции:
1. Считывание штрих-кода
2. Отправка информации в базу данных
3. Привязка пункта доставки к геопозиции устройства
 
 Тестовые сценарии
1. Считывание штрих-кода
   - Считать штрих-код из накладной и проверить, что приложение корректно отображает информацию о товаре.
   - Проверить, что приложение корректно обрабатывает различные форматы штрих-кодов.
   - Проверить, что приложение корректно обрабатывает ситуацию, когда штрих-код не найден в базе данных.
2. Отправка информации в базу данных
   - Проверить, что приложение корректно отправляет информацию о времени, геопозиции и номере накладной в базу данных.
   - Проверить, что приложение корректно обрабатывает ситуацию, когда отправка данных в базу данных не удалась.
3. Привязка пункта доставки к геопозиции устройства
   - Проверить, что приложение корректно определяет геопозицию устройства.
   - Проверить, что приложение корректно привязывает пункт доставки к геопозиции устройства.
   - Проверить, что приложение корректно обрабатывает ситуацию, когда определение геопозиции не удаётся.
Тестовая среда
- Операционные системы: Android (от 9 версии) и iOS (от 11 версии).
- База данных: MySQL.
Ожидаемый результат
- Мобильное приложение должно корректно работать на обеих платформах.
- Все основные функции должны работать без ошибок.
- Данные, отправленные в базу данных, должны быть корректными и полными.
 Заключение
После успешного выполнения всех тестовых сценариев и проверки всех основных функций, можно сделать вывод, что мобильное приложение готово к использованию.
##4 Составить чек-лист проверок 
Имеется раздел в приложении, содержащий два периода с указанием даты и времени. Тестировать по московскому времени. Запись в Базу данных происходит по времени UTC. 
Составить чек-лист проверок 
Имеется раздел в приложении, содержащий два периода с указанием даты и времени. Тестировать по московскому времени. Запись в Базу данных происходит по времени UTC. 

1. Проверка точности отображения дат и времени начала и конца периода в пользовательском интерфейсе.
2. Проверка точности отображения различия между временем начала и конца периода в пользовательском интерфейсе.
3. Проверка точности записи даты и времени начала периода в Базу данных (преобразование из Московского времени в UTC).
4. Проверка точности записи даты и времени конца периода в Базу данных (преобразование из Московского времени в UTC).
5. Проверка точности отображения даты и времени начала периода после чтения из Базы данных (преобразование из UTC в Московское время).
6. Проверка точности отображения даты и времени конца периода после чтения из Базы данных (преобразование из UTC в Московское время).
7. Проверка точности отображения различия между временем начала и конца периода после чтения из Базы данных.
8. Проверка корректности обработки ситуаций, когда начало периода позже его конца (должна быть ошибка).
9. Проверка корректности обработки ситуаций, когда дата и время начала периода находятся в прошлом (должна быть ошибка).
10. Проверка корректности обработки ситуаций, когда дата и время конца периода находятся в будущем (должна быть ошибка).

###5 Найти запросы на сайте 
1.	Добавление в корзину ( add to cart ) post запрос
2.	Удаление товара из корзины – post с последующим get запросом (если товаров в корзине не осталось)
3.	Пагинация по JS
4.	197px x 44px
