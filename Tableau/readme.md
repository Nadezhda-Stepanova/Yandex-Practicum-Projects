# Дашборд для Яндекс.Дзен

## Описание проекта
Источники данных для дашборда: cырые данные о событиях взаимодействия пользователей с карточками (таблица log_raw).
База данных, в которой будут храниться агрегированные данные: дополнительные агрегированные таблицы в БД zen.

Состав данных для дашборда:
- История событий по темам карточек (два графика - абсолютные числа и процентное соотношение);
- Разбивка событий по темам источников;
- Таблица соответствия тем источников темам карточек.

**Бизнес-задача**: анализ взаимодействия пользователей с карточками Яндекс.Дзен. 

Каждую карточку определяют её тема и источник, у которого тоже есть тема. Примеры тем: «Красота и здоровье», «Россия», «Путешествия». Пользователей системы характеризует возрастная категория, например, «26-30» или «45+». Способы взаимодействия пользователей с системой:
 Карточка отображена для пользователя (show);
 Пользователь кликнул на карточку (click);
 Пользователь просмотрел статью карточки (view).


**Техническая задача**:

- В Юпитере написать код для выгрузки данных из таблицы dash_visits в файл dash_visits.csv.
- В Tableau Public на основе файла dash_visits.csv сформировать дашборд в соответствии с макетом.
- Опубликовать дашборд на сайте Tableau Public. 

Ответить на вопросы, используя дашборд:
- Cколько взаимодействий пользователей с карточками происходит в системе с разбивкой по темам карточек?
- Как много карточек генерируют источники с разными темами?
- Как соотносятся темы карточек и темы источников?


## Импортируемые библиотеки:
- pandas
- sqlalchemy


## Результат
[Дашборд](https://public.tableau.com/app/profile/nadezhda8107/viz/education_dash_visits_project/Dash_project?publish=yes)

[Презентация](https://disk.yandex.ru/i/0XD3_aJHeR0gIA)
