В этом репозитории находится тестовое приложение, демонстрирующее возможности Yandex Map Kit.

Как начать
------------

1.  Клонируйте репозиторий примера
    git clone https://github.com/yandexmobile/yandexmapkit-android.git
2.  В папке yandexmapkit-library находятся библиотеки ресурсы и документация для Yandex Map Kit данный  проект является library project 
3.  В папке yandexmapkit-sample находится пример приложения который зависит от проекта yandexmapkit-library
4.  Данные проекты уже настроены для работы в среде Eclipse
 1.	Импортируйте данные проекты в среду Eclipse 
 2. Проверьте в настройках проекта yandexmapkit-library  в пункте Android  что установлена  "is Library"
 3. Проверьте в настройках проекта yandexmapkit-sample в пункте  Android что есть зависимость от проекта yandexmapkit-library
5.  Подставьте свой API ключ во все  layout где  используется объект MapView
6.  Всё готово к запуску тестового проекта

Использование с Maven
---------------------

Установите библиотеку в свой репозиторий или локально, с помощью `mvn clean install`.
После этого добавьте следующие строки в `pom.xml` своего проекта:

```xml
<dependency>
    <groupId>ru.yandex.android.yandexmapkit</groupId>
    <artifactId>library</artifactId>
    <version>2.0</version>
    <type>apklib</type>
</dependency>
<dependency>
    <groupId>ru.yandex.android.yandexmapkit</groupId>
    <artifactId>library</artifactId>
    <version>2.0</version>
    <type>jar</type>
</dependency>
```


Миграция с первой версии
-------------------------

1. При создании OverlayItem необходимо в конструкторе вместо объекта  Bitmap  передавать Drawable, можно воспользоваться new BitmapDrawable(you_bitmap)
2. При создании объекта BalloonItem необходимо в конструкторе передавать Context (необходимый для загрузки ресурсов)
3. Исправить использования интерфейса с OnBallonListener на OnBalloonListener и добавить новые методы из данного интерфейса
4. Исправить имя метода у BalloonItem с setOnBallonListener на setOnBalloonViewClickListener
5. Необходимо изменить логику работы интерфейса  OnBalloonListener  метода  onBallonClick  на  onBalloonViewClick


Интеграция проектов с Яндекс.Картами и Навигатором
--------------------------------------------------

Способы интеграции приложений с Яндекс.Картами для посторения маршрутов и выполнения поиска описаны на [Wiki](https://github.com/yandexmobile/yandexmapkit-android/wiki)

Дополнительная информация
---------------------------

Также у этого проекта есть:
* [Wiki](https://github.com/yandexmobile/yandexmapkit-android/wiki), в которой содержится полезная информация о Yandex Map Kit.
* JavaDoc, который находится в yandexmapkit-library/doc. В нем содержится описание классов и методов Yandex Map Kit.

Если вы хотите сообщить об ошибке или предложить идею в развитии, то напишите об этом, пожалуйста, в [Issues](https://github.com/yandexmobile/yandexmapkit-android/issues).
