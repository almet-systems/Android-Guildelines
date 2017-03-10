# 3 Архитектура

Рекомендуется использовать MVVM архитектуру в связке с Android Data Binding если иное не оговорено с заказчиком. 

## 3.1 Структура проекта

![logo]

[logo]: "/images/project_structure.png" "Структура проекта"

## 3.2 Примеры

Пример реализации экрана регистрации с проверкой полей
Пример реализации экрана списка новостей с отображением их списком
Пример реализации RecyclerView adapter с Android Data Binding и onClick событий на элементы


## Требования

* Обязательно создание BaseActivity, BaseFragment  и наследование от этих классов даже если на данный момент у вас нет общей логики для activity или fragment. 

* Обязательно выносить работу с базой в отдельные классы, чтобы viewModel не знал как устроена база в приложении и в любой момент можно было изменить название поля или тип данных не исследуя весь проект. 

* Все данные в базу должны сохраняться асинхронно и доставаться тоже асинхронно. 

## 3.3 Android Data Binding + MVVM FAQ

### *  В чем суть MVVM ?

__Ответ__:  Архитектура подразумевает разделение всего приложения на `Model`, `View` и `ViewModel`. 

`View` отвечает за отображение данных: это `xml layout` и `Activity`, `Fragment`. Там не должно быть обращения к api и к базе данных. Может содержать много viewModel. 

`Model` отвечает за модель данных и работу с ними (сохранение в нужном формате, получение в нужном формате). Это классы User, News, Api definition для работы с ними, Database implementation для работы с ними и т.д. `Model` не может обращаться `View` и на вход не должны передаваться `View` компоненты. 

`ViewModel` отвечает за связывание view и model. `ViewModel` связана с `View` через механизм binding. Для Android есть несколько реализаций, но мы используем реализацию Google - Android Data Binding. По Клику на кнопку или изменение текста `ViewModel` получает событие от `View`, получает данные от `Model` если это требуется и через механизм Binding или через шаблон Listener возвращает результат во View. Явной ссылки на `View` во `ViewModel` быть не должно. Может быть только ссылка на interface который `View` имплементирует.  

### *  В документации Android Data Binding есть много примеров как отображать данные но нет как их записывать во ViewModel. 

__Ответ__: Для почти всех стандартных компонентов (EditText, Checkbox и т.д) есть готовое решение записи текста

```xml
android:text="@={viewModel.nameField}"
```
В данном случае при старте текст для отображения в EditText будет браться из nameField, а при редактировании в него же записываться

### *  Для отображения данных нужно хранить не просто поле а вызывать метод, в котором есть какая-то логика. Этот метод вызывается только один раз, при установке viewModel. Как сделать так, чтобы при обновлении данных он тоже вызывался.

```xml
android:text="@{viewModel.getName()}"
```
__Ответ__: Для этого нужно все переменные (обязательно должны быть Observable), по изменению которых вы хотите обновлять текст, передавать как параметры в метод и, конечно, предусмотреть это в реализации метода. Обратите внимание, что на входе метода передаются уже не Observable объекты, а объекты, которые хранятся внутри Observable. 


Пример:

```xml
android:text="@{viewModel.getName(viewMode.nameField)}"
```

```java
public  String getName(String name){
	return name+”9999”;
}
```
## License

```
Copyright 2017 Almet-Systems Ltd.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
