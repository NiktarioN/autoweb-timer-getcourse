# autoweb-timer-getcourse
Таймер для автовебинаров на платформе GetCourse
Идеально подходит для автовебинаров, которые проходят каждый день в одно и тоже время

## Как работает стандартная настройка таймера?
* Таймер каждый день считает остаточное время до 19:00, в промежуток по времени 19:00 - 19:30, пользователя, попавшего на страницу с таймером, перебрасывает на указанную в скрипте страницу
* Когда таймер достигает время в 19:00, то он автоматически перезапускается и снова считает остаточное время до 19:00 следующего дня
* Пересылка идет на сайт https://getcourse.ru/
* Аргумент userHours = 19
* Аргумент userMinutes = 30
* Аргумент userUrl = 'https://getcourse.ru/'

## Как вставить таймер на страницу?
* Для этого используйте блок "Код HTML" в нужной форме и просто скопируйте туда код из документа

## Как настроить таймер под себя?
* Найдите в коде строчку setInterval(showTime, 1000, 19, 30, 'https://getcourse.ru/');
* Вместо цифры "19" напишите час, в который начинается вебинар
* Вместо цифры "30" напишите до какой минуты в часе будет происходить редирект на нужную для Вас страницу
* Вместо 'https://getcourse.ru/' вставьте ссылку, на которую хотите делать редирект во время начала вебинара

## Можно ли задать собственные стили таймеру? Сделать его по-своему?
* Да, в документе прописаны мои стили, вы их можете изменить сразу там, либо удалить и прописать их в стилях нужной формы, обращаясь к классу .timer-numbers

## Есть ли минусы у этого таймера?
* Да, есть один небольшой минус. Когда в определенный промежуток времени происходит редирект, то на странице с редактором он тоже будет происходить. Это связано с тем, что мы сразу наш таймер вставляем в нужное нам место на форме / странице как "Код HTML" и он сразу работает. Можно все содержимое в теге ```<script><script>``` перенести в конец страницы и вставить как "Код JavaScript". Тогда такой проблемы возникать не будет

## Что делать, чтобы не допустить ошибок в работе таймера?
* Не вводить параметр "Часы" больше 23 или любое отрицательное значение
* Не вводить параметр "Минуты" больше 59 или любое отрицательное значение
* Параметр с ссылкой на редирект вводить только через одинарные или двойные ковычки полной ссылкой
