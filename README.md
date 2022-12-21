# Module-28-Finall-project
Функциональное и UI тестирование сайта https://b2c.passport.rt.ru/ Описание того, что именно делает конкретный тест, можно найти в коде самих тестов

Для запуска необходимы библиотеки pytest, selenium (версия 4) и webdriver для браузера (в проекте приложен драйвер для браузера Chrome 108 версии). Если версия вашего браузера отличается от 108, то необходимый драйвер можно скачать по ссылке https://chromedriver.chromium.org/downloads

Команда для запуска тестов: pytest -v --driver Chrome --driver-path <путь до webdriver> 

Пример: pytest -v --driver Chrome --driver-path D:/chromedriver.exe

______________________________________________________________________________________________________

Что не получилось:
1) Сделать фикстуру инициализации. Тесты не видели переменных driver и wait.

2) Нет четкого понимания когда и какие использовать ожидания, поэтому используются везде. Опытным путем выяснилось, что EC работают не всегда. Пример: тест test_successful_authorization. Элемент с фамилией пользователя появляется сразу, но текст подгружается с задержкой. Пришлось использовать time

3) Проверить, что конкретный элемент находится в конкретном месте. (Пример: элемент Х находится в левой части страницы)

4) Проверить наличие элементов, которых нет вообще. (Пример: кнопка "X" на странице "Учетная запись уже существует", лого и слоган в тесте test_registration_page_all_elements_are_visible)

5) Написать некоторые надежные локаторы, если нет id. Длинные названия классов selenium почему-то не воспринимает. (Пример: элемент AUTHORIZATION_TAB_MENU) 
