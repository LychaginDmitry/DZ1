# Методические указания по выполнению домашнего задания №1.
## Команда курса благодарит Звонарева Алексея и Лычагина Дмитрия за активное участие в подготовке данного руководства.
## Задание
Необходимо создать и разметить собственный набор данных, состоящий из изображений. Набор содержит не менее 3 классов и не менее 100 экземпляров каждый. Изображения можно скачать из интернета или объединить несколько существующих датасетов. Создать web-приложение для классификации изображений полученного набора данных. Использовать аугментацию данных, регуляризацию, перенос обучения. Пример создания простого web-приложения на Django.
## Контрольные вопросы
1. Структура набора данных, аугментация данных.
2. Перенос обучения, дообучение.
3. Архитектура сверточной нейронной сети.
## Установка IDE PyCharm Professional
Для выполнения лабораторной работы потребуется [PyCharm Professional](https://www.jetbrains.com/pycharm/download/#section=windows//).

Студенческую лицензию можно получить, указав бауманскую почту.
## Часть 1. Загрузка изображений
+ **Вариант 1**. Требуется установить одно из расширений Chrome: [Image downloader - Imageye](https://chrome.google.com/webstore/detail/image-downloader-imageye/agionbommeaifngbhincahgmoflcikhm?hl=en-US//) или [Image Downloader](https://chrome.google.com/webstore/detail/image-downloader/cnpniohnfphhjihaiiggeabnkjhpaldj?hl=en-US//). После установки найти изображения в одной из поисковых систем, затем при помощи загруженного ранее расширения загрузить картинки.
+ **Вариант 2**. Требуется установить библиотеку Python: [yandex-images-download](https://pypi.org/project/yandex-images-download/?msclkid=b0148afab45011ec8358c9751dabcf63//) ([GitHub](https://github.com/doevent/yandex-images-downloader/?msclkid=b0155486b45011eca4a25458cfa90a0e//)). После установки библиотеки необходимо скачать [ChromeDriver](https://chromedriver.chromium.org/?msclkid=c622b0f0b45011ec8c6768a6d02ae314//) для Вашей версии Google Chrome и распаковать файл chromedriver.exe. 



