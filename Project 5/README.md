## **Описание проекта:**
Cтартап, который продаёт продукты питания. Нужно разобраться, как ведут себя пользователи вашего мобильного приложения.
Цель исследования:
- изучение воронки продаж,
- изучение результатов A/A/B-эксперимента,
- выводы.
Ход исследования:
первая задача состоит в том, чтобы изучить воронку продаж. Нам требуется узнать какой путь проходят пользователи до покупки и сколько из них "застревает" на каждом из этапов этого пути,
дизайнеры решили изменить шрифты в приложении, но учитывая радекальность этого решения, перед его воплощением провели A/A/B-эксперимент.
Нам надо изучить его результаты, обратив внимание на идентичность групп A. Описание данных:
Каждая запись в логе — это действие пользователя, или событие.
- EventName — название события;
- DeviceIDHash — уникальный идентификатор пользователя;
- EventTimestamp — время события;
- ExpId — номер эксперимента: 246 и 247 — контрольные группы, а 248 — экспериментальная.

## **Основные инструменты:**
Python (pandas, matplotlib, scipy)

## **Итоговый вывод:**
- Мы определили, что в таблице 244126 события, 7551 уникальных пользователя, на одного пользователя в среднем приходится 32 события, в нашей таблице данные за 13 дней, данные до 01 августа были удалены для исправления перекоса. Было удалено 17 пользователей и 2828 событий. В нашей таблице присутствуют достаточно все группы пользователей, они достаточно одиноковым количеством.
- Наиболее частое событие - MainScreenAppear (переход на главный экран) - 117328 действий пользователей, что составляет 48.71% от общего числа событий. CartScreenAppear совершали лишь 42303 раза или 17.56% от общего числа событий. PaymentScreenSuccessful товара совершали 33918 раза или 14.08% от общего числа событий, больше всего пользователей теряется при переходе с главного экрана в каталог товаров - 38,1%, от первого события переход на главный экран до события успешная оплата заказа переходит 47,7% всех пользователей.
- После изучения воронки продаж, мы перешли к исследованию результатов A/A/B-тестов. A/A/B-тест применяется когда трафик делят на три части: первую и вторую направляют на сайт без изменений, а третью с изменениями. Таким образом, пользователей разбили на 3 группы: 2 контрольные группа 246 (2484 участника) и группа 247 (2513 участника) со старыми шрифтами и одну экспериментальную группу 248 (2537 участника) — с новыми. Также, дополнительно была создана обьединённая группа 249 (4997 участника) из двух контрольных групп, котора способствует точности проведенного тестирования. Целью A/A/B-тестов было одобрение или отклонение изменения шрифта во всём приложении.
- Подводя итоги можно сказать, A/A/B-тесты можно считать успешно завершенными, изменение шрифта никак не повлияло на поведение пользователей приложения, они одинаково совершают переходы по воронке событий, вне зависимости есть или нет изменения шрифта. Поэтому, дизайнеры могут поменять шрифты во всём приложении, а менеджеры могут не опасаться, о том, что пользователям будет непривычно.
