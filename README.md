# Книжный интернет-магазин на API Google Books

# ЗАДАЧА ПРОЕКТА

В рамках проекта необходимо:

Сверстать главную страницу интернет-магазина Bookshop.
Подключить Google Books API так, чтобы данные о книгах подгружались с сервера.
Подключить слайдер.
Поработать над правильной организацией проекта.

# ФУНКЦИОНАЛЬНЫЕ ТРЕБОВАНИЯ

# Шапка сайта
Шапка содержит логотип, навигацию и набор кнопок. Ссылки в меню можно оставить пустыми, так как реализация остальных страниц сайта в проекте не предусмотрена.

Кнопки авторизации, поиска и корзины неактивны. Однако при добавлении товара в корзину у иконки должен появиться бейджик с количеством товара в корзине.

При прокрутке сайта шапка должна оставаться закреплённой в верхней части экрана.


# Слайдер
Под шапкой сайта располагается слайдер. Чтобы сократить время разработки, рекомендуем вам использовать слайдер, которые вы создали при прохождении модулей по JavaScript.

Слайдер автоматически пролистывает изображения каждые 5 секунд, а после последнего изображения вновь переключается на первое. Перелистывать изображения можно также с помощью точек под слайдером.

Справа от слайдера располагаются цветные блоки. Их нужно сверстать как ссылки, адреса ссылок можно оставить пустыми.

# Список категорий и список книг
Под слайдером в левой части экрана располагается список категорий. Активная категория должна быть выделена визуально.

По умолчанию в качестве активной выбрана первая категория в списке. Клик на неактивную категорию делает её активной, и список книг перезагружается, чтобы отобразить книги из этой категории.

Список книг подгружается из Google Books API в соответствии с выбранной категорией. Для списка книг необходимо реализовать ленивую загрузку: сначала подгружаются первые 6 книг, по клику на кнопку «Load more» — ещё 6, и так далее.

# Карточка книги
В карточке книги должна быть отображена следующая информация:

Обложка. Если API не возвращает обложку, подставить вместо неё любую картинку-плейсхолдер.
Автор. Если авторов несколько, перечислить их через запятую.
Заголовок.
Рейтинг: от 1 до 5 звёздочек плюс общее количество отзывов. Если в данных о книге нет рейтинга, не показывать эту строчку.
Описание. Если текст в описании занимает больше 3-х строк, его нужно обрезать и добавить в конце многоточие.
Цена с указанием валюты. Если в данных о книге нет цены, не показывать эту строчку.
Ниже приведён пример карточки товара, а также названия свойств в объекте книги, которые содержат необходимую информацию:

Под описанием каждой книги должна быть кнопка «Buy now». При клике на неё товар добавляется в корзину, а кнопка меняет внешний вид. При повторном нажатии на кнопку товар убирается из корзины.

Информация о книгах, добавленных в корзину, должна сохраняться в localStorage.

# ТЕХНИЧЕСКИЕ ТРЕБОВАНИЯ

Книжный магазин должен быть реализован по принципу SPA. 
То есть все действия пользователя: подгрузка книг, переключение категории — происходят без перезагрузки страницы.

JS-файлы в проекте должны быть разделены на модули (ES6), структура файлов должна быть логичной и понятной.

Для создания проекта необходимо использовать npm. В папке проекта должны быть файлы package.json и package-lock.json. В package.json необходимо прописать скрипт npm run build, который будет запускать сборку проекта.

К проекту необходимо подключить Webpack. 
Если запустить сборку проекта, ожидается следующий результат:
сборка завершается успешно и без ошибок;
CSS-файлы также является частью сборки;
CSS подключается отдельным файлом, не в теге <style>;
JS и CSS-файлы минифицируются в процессе сборки.

В проекте необходимо использовать ещё как минимум 2 инструмента оптимизации разработки (помимо npm и Webpack), которые вы прошли в предыдущих модулях. Вы можете выбрать любые из списка:
методология БЭМ;
CSS-препроцессор Sass (или аналог);
Шаблонизатор pug или аналог;
Webpack Dev Server;
Линтер.

# ТРЕБОВАНИЯ К ВЁРСТКЕ И CSS

Вёрстка должна соответствовать макету. Добиваться Pixel-Perfect соответствия не обязательно, но основные моменты должны быть соблюдены:
цветовая гамма,
шрифты,
размеры,
отступы.

Использовать селекторы по тегу и id для задания стилей нельзя. Используйте классы.

При наведении курсора на любые кликабельные элементы должен появляться cursor: pointer.

Соблюдайте семантическую вёрстку.
В приложении должны присутствовать разделы <header>, <main> и <nav>. Ссылки должны быть прописаны в теге <a>, кнопки должны быть реализованы элементом <button>, и так далее. Не забывайте также про обязательный атрибут alt у изображений.

Приложение должно корректно отображаться на различных разрешениях. К сожалению, дизайна для мобильной версии в макете нет, поэтому постарайтесь реализовать её самостоятельно.
Не нужно придумывать сложный дизайн, достаточно будет просто перегруппировать элементы так, чтобы они помещались на маленьком экране.

# КАК ЗАПУСТИТЬ ПРОЕКТ

Запустить в консоле команду npm run build, после сборки проекта запустить index.html из папки dist