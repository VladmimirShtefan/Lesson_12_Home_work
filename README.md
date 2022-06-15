## Задание. Домашняя работа №12. #Flask #blueprint #search #loggining

# Урок 12. Домашнее задание

В этом задании вам предстоит написать небольшой проект, связанный с постами и формами. Часть своего решения вы сможете использовать в курсовой работе этого курса. Устроен проект так:


На главной странице находится поле поиска: когда пользователь вводит текст и нажимает "Найти", то получает список постов, в тексте которых содержится подстрока, которую пользователь ввел.  Также пользователь может перейти к добавлению поста. На странице пользователь может ввести текст и выбрать картинку. После отправки, текст и картинка будут показаны, а пост попадет в список постов.

**Список страниц:**

---

`/` – главная страница (поиск постов)

`/search/?s=поиск` – страничка ленты по тегу

`GET /post` – страничка добавления поста

`POST /post` – страничка после добавления поста

---

**Шаг 1.** 

Склонируйте проект и изучите шаблоны и структуры папок.

`uploads` – папка для загруженных файлов, загружайте все в нее

`static` – папка для статики, например стилей

`templates` – папка для шаблонов

`posts.json` – файл с данными постов 

Создайте два блюпринта:

`main` - для показывания фото

`loader` - для загрузки фото

**Шаг 2.** 

Начните работу над блюпринтом `main`, создайте, импортируйте, зарегистрируйте его.

Реализуйте вывод формы на главной странице при обращении к `/`

Испольузуйте шаблон `index.html`

Не забудьте перенести и подключить стили из папки со статическими файлами! 

**Шаг 3.**

Реализуйте поиск и вывод постов при обращении на `/search/?s=<ключ поиска>` 

Испольузуйте шаблон `post_list.html`

Чтение из файла и поиск постов лучше вынести в отдельные функции.

Не забудьте переписать ссылки на стили! 

**Шаг 4.**

Продолжите работу в блупринте `loader`, создайте, импортируйте, зарегистрируйте его.

Реализуйте страничку "добавить пост" при обращении к `GET /post`

Испольузуйте шаблон `post_form.html`

Не забудьте переписать ссылки на стили! 

**Шаг 5.**

Обработайте запрос при обращении к `POST /post`

Положите загруженный файл в папку `uploads`

Добавьте список постов в файл `posts.json`

Запись в файл лучше вынести в отдельные функции.

Если загрузка произошла, выведите пост и фотографию.

Испольузуйте шаблон `post_uploaded.html`

Если не была отправлена, выведите сообщение "ошибка загрузки" без шаблона

Не забудьте перенести и подключить стили из папки со статическими файлами! 

**Шаг 6.**

Добавьте обработку следующих ошибок:

- Файл `posts.json` отсутствует или не хочет превращаться в список
- Загруженный файл - не картинка (расширение не jpeg и не png)
- Ошибка при загрузке файла

**Шаг 7.**

Добавьте логирование в готовый проект:

`info` – при выполнении поиска

`info` – если загруженный файл - не картинка

`error` если ошибка при загрузке файла

### Подсказки:

При загрузке кириллицы через json.dump() используйте `ensure_ascii=False`

В исходном коде уже добавлена вьюшка для отдачи загруженных в /uploads файлов

### Критерии проверки:

- [ ]  Шаблоны использованы корректно
- [ ]  Формы используют правильные методы
- [ ]  Загрузка файлов реализована корректно
- [ ]  Загруженные файлы отдаются корректно
- [ ]  Есть проверки  того, что данные отправлены