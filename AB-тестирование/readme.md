## А/В-тестирование

Задача: провести оценку результатов A/B-теста. Есть датасет с действиями пользователей, техническое задание и несколько вспомогательных датасетов. 
Надо:
- Оценить корректность проведения теста
- Проанализировать результаты теста
 
Проверить:
- пересечение тестовой аудитории с конкурирующим тестом,
- совпадение теста и маркетинговых событий, другие проблемы временных границ теста.

## Используемые библиотеки:
- pandas
- datetime
- numpy 
- math 
- matplotlib
- seaborn 
- scipy 
- plotly 
- statsmodels

**Техническое задание**
- Название теста: recommender_system_test;
- группы: А — контрольная, B — новая платёжная воронка;
- дата запуска: 2020-12-07;
- дата остановки набора новых пользователей: 2020-12-21;
- дата остановки: 2021-01-04;
- аудитория: 15% новых пользователей из региона EU;
- назначение теста: тестирование изменений, связанных с внедрением улучшенной рекомендательной системы;
- ожидаемое количество участников теста: 6000.
- ожидаемый эффект: за 14 дней с момента регистрации пользователи покажут улучшение каждой метрики не менее, чем на 10%: 
-- конверсии в просмотр карточек товаров — событие product_page,
-- просмотры корзины — product_cart,
-- покупки — purchase.


## Общие выводы 
 
- Тест следует  признать проведенным не совсем корректно, так как при его проведении были нарушены следующие условия:
    - Время проведения теста попало на маркетинговую акцию.
    - Имел место не полный сбор данных, выражающийся в записи событий исключительно после ввода логина пользователем.
    - Одновременно проводился еще один тест, возможно, повлиявший на результаты, так как аудитория теста пересекается с конкурирующим тестом.
    - В тест попали пользователи не только из EU, но и из других регионов.
    
Ожидание, что аудитория составит 15% новых пользователей из региона EU, оправдались.

- Зафиксировано следующее различие между группами:
    - Разница конверсий в просмотр карточек (product_page) является статистически значимой, у контрольной группы А конверсия выше. 
    - Разница конверсий у остальных событий не является статистически значимой.
 
В итоге эксперимент следует признать не удавшимся, так как вопреки ожиданиям от новой платежной воронки на улучшение каждой метрики на 10% имеет место либо ухудшение конверсии, либо показаны результаты, соответствующие контрольной группе.

**Рекомендации**

- При проведении тестов в будущем следует учитывать время их проведения во избежание совпадения с маркетинговыми акциями. 
- Даже просто праздничные дни, такие как, например, Рождественские каникулы, полностью меняют поведение клиентов и отражаются, скажем, на спонтанности покупок, большей ценовой категории покупок в подарок, времени в приложении и тому подобном. Такие моменты следует исключать.
- Проведение двух тестов одновременно может исказить данные, рекомендовано к проведению не более одного теста в один промежуток времени.
- Следует соблюдать чистоту тестов по регионам, как в данном случае, а в целом по любому другому значащему признаку. 
- Изменения для новой воронки пользователей следует признать не успешными, эксперимент провалился.
