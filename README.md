
![instapi-followers](/readme/images/banner.jpg)

# Instapi-followers
**Версия:** 1.0<br>
**Описание:** Instagram-парсер, сбор подписчиков и подписок на основе fetch-запросов с интерфейсом управления и возможностью скачать данные в формате JSON или Excel (CSV)<br><br>
[![buymeacoffee](/readme/images/buymeacoffee.png)](https://pay.mysbertips.ru/72317565)

### Состав проекта:
- каталог [`/readme/images`](/readme/images/) содержит изображения для файла [`readme.md`](README.md)
- каталог [`/src-interface`](/src-interface) содержит исходный код интерфейса
- файл [`instapi-followers.js`](instapi-followers.js) - полный код скрипта
- файл [`instapi-followers.min.js`](instapi-followers.min.js) - предпочтительный (сжатый)

### Во избежание блокировки
> Старайтесь не использовать личный аккаунт для сбора данных и не превышайте лимиты Instagram. Сбор данных осуществляется только с открытого аккаунта, либо вы должны быть на него подписаны.

## Как запустить?
На примере браузера Google Chrome
1. В браузере переходим в [https://instagram.com](https://instagram.com) и авторизуемся
2. Далее переходим на страницу интересующего аккаунта
3. Открываем в браузере **инструменты Разработчика**<br>
<sub>(CTRL-SHIFT-J для Windows, OPTION-COMMAND-J для MacOS)</sub>
4. После, в открывшемся окне, переходим на вкладку **Консоль (Console)**
5. В открывшуюся консоль, вставляем код скрипта:<br><br>
[`instapi-followers.js`](instapi-followers.js) <sub>- полный код скрипта</sub><br>
[`instapi-followers.min.js`](instapi-followers.min.js) <sub>- предпочтительный (без лишнего и сжатый)</sub><br><br>
6. Нажимаем клавишу **ENTER** и на странице появится интерфейс парсера
7. Настраиваем параметры сбора и нажимаем на кнопку **СТАРТ**

## Интерфейс и параметры настройки
В интерфейсе парсера по-каждому параметру настройки написано примечание.<br>
Разберем каждый параметр в отдельности.

![full-parser](/readme/images/instaparser_01.jpg)

## Информация и параметры по аккаунту сбора
![first-block](/readme/images/instaparser_02.jpg)
<br>
В данном разделе представлена общая **информация по аккаунту** сбора, 
а также параметры настройки **Сбор данных** и **Формат данных**<br><br>
### Информация по аккаунту<br>
1. Изображение аккаунта
2. Название аккаунта
3. ID аккаунта
4. Доступность аккаунта для сбора: <br><br>
`Открытый` <sub>- сбор разрешен</sub> <br>
`Закрытый (подпишитесь)` <sub>- сбор запрещен, нужно сначала подписаться</sub> <br>
`Закрытый (подписаны)` <sub>- сбор разрешен, аккаунт подписан</sub><br>
<br>
5. Кол-во подписчиков
6. Кол-во подписок
7. Кол-во публикаций

### Сбор данных
На выбор два варианта: **Подписчики** или **Подписки**<br>
Выберете тот вариант, который Вам требуется.<br><br>
**Примечание:** при переключении, параметра сбора данных, будет сброшен текущий сбор 
(кол-во собранных аккаунтов, время сбора) и сам файл данных для загрузки. 
Общее кол-во отправленных запросов останется неизменным.

### Формат данных
На выбор два варианта: **Формат JSON** или **Формат Excel (CSV)**<br>
Выберете тот вариант, который Вам требуется.<br><br>
**Примечание:** переключать формат данных можно в любой момент времени - этот 
параметр не влияет на поведение парсера. Данный параметр привязан к кнопке
**Скачать данные**, а от выбора зависит формат файла при скачивании собранных данных.

## Ограничение кол-ва запросов
![limit-requests](/readme/images/instaparser_03.jpg)
<br>
В данном разделе представлен параметр отвечающий за **ограничение кол-ва запросов** 
при сборе данных. Ограничение нужно, чтобы не попасть под блокировку.<br><br>
**Лимиты Instagram:** в сутки, с вашего зарегистрованного аккаунта, можно сделать не более 150-500 запросов 
на сбор данных (это примерно 15-50К аккаунтов, которые можно собрать). **Рекомендуемое кол-во запросов: 150** 
на сбор в сутки с одного аккаунта.
<br><br>
**Примечание:**  чтобы полностью убрать ограничение парсера на кол-во
запросов - очистите значение в поле или поставьте 0.

## Имитация человека
![imitation](/readme/images/instaparser_04.jpg)
<br>
В данном разделе представлен параметр отвечающий за возможность отправки запросов с разными интервалами (от 1 до 8 секунд), 
т.е. **имитирует деятельность человека, а не программы** при сборе данных. По умолчанию запросы отправляются без задержек.
<br><br>
**Примечание:**  используйте этот параметр, чтобы уменьшить риск блокировки аккаунта со стороны Instagram, но время сбора
данных увеличится. Данный параметр можно **включать/отключать** в любой момент времени.

## Точка остановки и кнопка СТАРТ
![endpoint](/readme/images/instaparser_05.jpg)
<br>
В данном разделе представлен параметр отвечающий за возможность начать сбор данных с места прерывания - **Точка остановки**
 и кнопка запуска работы самого парсера - кнопка **СТАРТ**.<br>

### Точка остановки
При сборе данных, в поле будет появляется код, который служит отметкой кол-ва собранных аккаунтов.
Так как в Instagram "списки" подписчиков/подписок пополняются последовательно (новые подписавшиеся всегда сверху "списка"),
то данный код служит именно отметкой в этих "списках". Т.е. имея код-отметку, можно начинать сбор именно с того места в "списке",
где он был сформирован. <br><br> 
**Пример 1:** у аккаунта сбора 7000 подписчиков, при сборе данных допустим вы собрали уже 3500 подписчиков
и принудительно остановили сбор, нажав кнопу **СТОП**. в поле **Точки остановки** есть код. Если нажать снова **СТАРТ**, 
то сбор продолжится не сначала, а с 3500 подписчиков и будет дополнятся в файл данных для скачивания.
<br><br> 
**Пример 2:** допустим вы запустили сбор данных, данные собираются, но что-то пошло не так (отключили интернет, вылезла ошибка лимитов и т.д.).
В итоге вы всегда можете скачать данные, а сохранив код **Точки остановки** и перейдя позже в аккаунт сбора, вставив данный код в поле - у вас 
начнется сбор данных именно с того места, где было прерывание. Но файл данных, при загрузке, будет уже новый и именно с той отметки сбора.
<br><br>
**Примечание:** если удалить код-отметку **Точки остановки**, то файл данных будет сброшен и сбор начнется с начала.

### кнопка: СТАРТ
Это кнопка запуска работы сбора данных. <br>
Кнопка имеет три состояния: **СТАРТ**, **СТОП** и **ГОТОВО**: <br><br>
`СТАРТ` <sub>- запуск сбора данных</sub> <br>
`СТОП` <sub>- остановка сбора данных</sub> <br>
`ГОТОВО` <sub>- появляется при выполнении сбора данных</sub><br>

## Статистика и сохранение данных
![statistics](/readme/images/instaparser_06.jpg)
<br>
В данном разделе представлены краткая информация по статистике сбора данных и кнопка для скачмвания собранных данных **Скачать данные**.

### Статистика
Представлены 3 информационных параметра:<br><br>
`Кол-во запросов` <sub>- общее кол-во отправленных запросов</sub> <br>
`Собрали аккаунтов` <sub>- кол-во аккаунтов собранных за текущий сбор</sub> <br>
`Время сбора` <sub>- время сбора за каждый запуск работы парсера</sub><br>

**Примечание:** при каждом нажатии кнопки **СТАРТ**, параметр **Кол-во запросов** остается неименным, параметр **Собрали аккаунтов** - будет неизменным, 
если не переключали параметр **Сбор данных**, параметр **Время сбора** - всегда показывает только время текущего сбора.

### кнопка: Скачать данные
Данная кнопка отвечает за скачивание собранных данных. Кнопка связана с параметром **Формат данных**, при изменении данного параметра, файл данных будет
именно в том формате, который выбрали.

# Консоль
![console](/readme/images/instaparser_07.jpg)
<br>
В консоле браузера, выводятся логи работы парсера, данные по отправленным запросам и разного рода техническая информация,
включая ошибки.

# Дисклеймер
>Я не несу ответственности за ваши действия. Скачивание, использование, распространение программного обеспечения из этого репозитория - является вашей зоной ответственности.

#
[Telegram](https://t.me/leoneedpro) |
[Instagram](https://instagram.com/leoneedpro) |
[Youtube](https://youtube.com/@leoneedpro) |
[Вконтакте](https://vk.com/leoneedstudio)