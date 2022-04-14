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
## Часть 1
### Загрузка изображений
+ **Вариант 1**. Требуется в одной из поисковых систем найти картинки по требуемым классам, затем скачать вручную в 3 разные папки.
+ **Вариант 2**. Требуется установить одно из расширений Chrome: [Image downloader - Imageye](https://chrome.google.com/webstore/detail/image-downloader-imageye/agionbommeaifngbhincahgmoflcikhm?hl=en-US//) или [Image Downloader](https://chrome.google.com/webstore/detail/image-downloader/cnpniohnfphhjihaiiggeabnkjhpaldj?hl=en-US//). После установки найти изображения в одной из поисковых систем, затем при помощи загруженного ранее расширения загрузить картинки.
![image](https://user-images.githubusercontent.com/43611343/161835583-0ccab8c7-663f-40ef-a21c-891120852419.png)
#### Шаг 1
В любой из поисковых систем выполнить поиск картинок на интересующую тему.
#### Шаг 2
Открыть ранее установленное расширение.
#### Шаг 3
Выбрать тип изображения JPG.
#### Шаг 4
Выбрать все картинки и скачать.
+ **Вариант 3**. Требуется установить библиотеку Python: [yandex-images-download](https://pypi.org/project/yandex-images-download/?msclkid=b0148afab45011ec8358c9751dabcf63//) ([GitHub](https://github.com/doevent/yandex-images-downloader/?msclkid=b0155486b45011eca4a25458cfa90a0e//)). После установки библиотеки необходимо скачать [ChromeDriver](https://chromedriver.chromium.org/?msclkid=c622b0f0b45011ec8c6768a6d02ae314//) для Вашей версии Google Chrome и распаковать файл chromedriver.exe. В командной строке PyCharm ввести следующую команду: *yandex-images-download Chrome --keywords "Торт, Ласточка, Кошка" --limit 100* (пример альтернативной команды: *yandex-images-download Chrome --keywords "ласточка, орёл, торты" -o путь_для_скачивания -l количество фотографий -dp путь_к_chromedriver.exe*).
### Валидация изображения
После успешной загрузки изображений требуется очистить лишние объекты в ручном режиме на предмет возможных ошибок (дубликация, неверная тематика).
### Импортирование изображений в Google Colab 
#### Шаг 1
Требуется перейти по ссылке на подготовленный [проект](https://colab.research.google.com/drive/1eMUdI_cAvc9u0bPLXCrPJvq1Ngp4yLdI?usp=sharing#scrollTo=k7OkUQAlZMua//) и сохранить себе копию на Google диск.
#### Шаг 2
В файловой системе Colab-файла в папке "content" необходимо создать три папки, согласно классам тематики Ваших изображений (пример: "Торт, Ласточка, Кошка") и загрузить туда скаченные ранее изображения. 
![image](https://user-images.githubusercontent.com/43611343/161836816-5122f961-dfee-4f48-80e8-8567521401e7.png)

Открываем файловую систему в Colab (автоматически откроется папка "content"). Нажимаем ПКМ в свободном пространстве и создаем папки по тематике классов.
#### Шаг 3
Изменить переменную класса под свою тематику.
### Модернизация исходной модели в Colab
Требуется выполнить аугментацию, регуляризацию и перенос обучения и сохранить модель в формате ONNX.
## Часть 2
### Создание web-приложения для классификации изображений полученного набора данных
#### Шаг 1
Пример создания проекта Django в IDE Pycharm можно просмотреть по данной [ссылке](https://github.com/iu5team/iu5web-fall-2021/blob/main/tutorials/lab4/lab4_tutorial.md#%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%83%D0%BA%D0%B0%D0%B7%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D1%8E-%D0%BB%D0%B0%D0%B1%D0%BE%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B9-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B-4//).
#### Шаг 2
После создания проекта требуется создать в корне проекта папку media для последующего сохранения изображений и файлов формата ONNX. Внутри папки media необходимо создать папки "images" и "models".

![image](https://user-images.githubusercontent.com/43611343/163047562-ff3f4178-d9cc-4a10-9b9f-efaaab5eeae7.png)
#### Шаг 3
В файл setting.py требуется добавить пути к ранее созданной папке media. В самом конце необходимо добавить следующий блок код:

![image](https://user-images.githubusercontent.com/43611343/163047087-974cc6b0-9691-44dc-a750-980ffe85600a.png)
#### Шаг 4
Добавить Python файл views.py в ту же папку, где был файл setting.py.

Здесь будет ссылка на файл...

![image](https://user-images.githubusercontent.com/43611343/163046056-3f32d871-6e00-4078-9b5d-b7080d447999.png)

##### Шаг 4.1
В файле views.py изменить классы по Вашей тематике и указать путь к модели ONNX.

![image](https://user-images.githubusercontent.com/43611343/163056856-37a6f80f-3068-401e-9c7e-873a24ed7669.png)

![image](https://user-images.githubusercontent.com/43611343/163248523-05e05fb6-8622-4747-9a54-04864572862f.png)
#### Шаг 5
В файле urls.py требуется заменить содержимое на следующий блок кода:

![image](https://user-images.githubusercontent.com/43611343/163247855-b5a0c9ac-67e6-444e-8956-63bdfcc841d0.png)
#### Шаг 6
Установить следующие библиотеки: onnx, onnxruntime, numpy, pillow.
Пример установки одной библиотеки:

![image](https://user-images.githubusercontent.com/43611343/163048370-a731e483-60ed-4db4-89a3-e57f788b5fbd.png)
#### Шаг 7
В папку templates добавить файл scorepage.html.

Здесь будут ссылка на файла...
#### Шаг 8
Запустить проект, выполнив в терминале PyCharm следующую команду: "python3 manage.py runserver".

#### Шаг 9
Загрузить изображение и нажать на кнопку "submit".

![image](https://user-images.githubusercontent.com/43611343/163248372-bc89f118-d947-43f2-b8e0-ceee11faf5c7.png)

"```python
def predictImage(request):
    fileObj = request.FILES['filePath']
    fs = FileSystemStorage()
    filePathName = fs.save('images/'+fileObj.name,fileObj)
    filePathName = fs.url(filePathName)
    modelName = request.POST.get('modelName')
    scorePrediction = predictImageData(modelName, '.'+filePathName)
    context = {'scorePrediction': scorePrediction}
    return render(request, 'scorepage.html', context)
```"
