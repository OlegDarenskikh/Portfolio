# Исследование гипотез

## Задача 

Приоритизировать гипотезы, запустить A/B тест одной из гипотез и проанализировать результаты.

## Данные

Данные первой части:

- Файл `hypothesis`

    * `Hypothesis` — краткое описание гипотезы;
    * `Reach` — охват пользователей по 10-балльной шкале;
    * `Impact` — влияние на пользователей по 10-балльной шкале;
    * `Confidence` — уверенность в гипотезе по 10-балльной шкале;
    * `Efforts` — затраты ресурсов на проверку гипотезы по 10-балльной шкале.
    

Данные второй части:

- файл `orders`

    * `transactionId` — идентификатор заказа;
    * `visitorId` — идентификатор пользователя, совершившего заказ;
    * `date` — дата, когда был совершён заказ;
    * `revenue` — выручка заказа;
    * `group` — группа A/B-теста, в которую попал заказ.

- файл `visitors`

    * `date` — дата;
    * `group` — группа A/B-теста;
    * `visitors` — количество пользователей в указанную дату в указанной группе A/B-теста.

## Общий вывод

1. В первую очередь следует обратить внимание на гипотезы:
* "Добавить форму подписки на все основные страницы, чтобы собрать базу клиентов для email-рассылок"
* "Добавить два новых канала привлечения трафика, что позволит привлекать на 30% больше пользователей"

Другие же гипотезы будут значительно уступать данным, в основном из-за охвата пользователей.

2. В части анализа А/В теста:
* Есть статистически значимое различие в конверсии между группами А и В, как в сырых, так и в очищенных данных. Группа В превышает по этому показателю группу А на 18,4%;
* Группа А опережает группу В в среднем чеке, но как по сырым так и по очищенным данным, но по нашим расчетам, мы не можем считать эти значения статистически значимыми;
* График относительного изменения кумулятивной конверсии группы B к группе A показывает, что результаты группы В стабильно лучше группы А. Хоть при наличи выбросов такой график сложно считать показательным, он позволил обнаружить это влияние.

На основании вышеизложенного рекомендуем остановить тест, зафиксировав победу группы B, так как относительный прирост конверсии значительно выше.

## Используемые библиотеки

`Python` `Pandas` `Numpy` `Matplotlib` `Seaborn` `Math` `scipy.stats` `предобработка данных` `визуализация данных` `проверка статистических гипотез` `АВ-тест` `АА-тест`
