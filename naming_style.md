# 1. Гайд по наименованию


### 1.1 Классы

* Activity - `{Name}Activity` (`SignInAcitivity.java`)
* Fragment `{Name}Fragment` (`NewsFragment.java`)
* Dialog `{Name}Dialog` (`TimeChooseDialog.java`)
* Adapter `{Name}Adapter` (`NewsAdapter.java`)

Интерфейсы: должны начинаться с большой буквы I. Пример `IActionListener`, `IPresenter`

### 1.2  Ресурсы

Названия файлов ресурсов должны быть написанны в нижнем регистре используя подчеркивание для разделения слов

Название для ресурсов должны назначаться исходя из того, где они используются, а не того, как они выглядят
```diff
- `btn_red` -неправильно

+ `btn_delete`- правильно 
```

Если одна кнопка (или другой компонент) используется на многих экранах, то можно использовать, например

`btn_primary_action_default`

#### Png icons
Названия должны начинаться с `ic_{где используется}`. 
Пример: `ic_close`, `ic_copy.`

#### Background selector for button :  
`btn_create_request.xml`

 Drawable button state: 
 
* normal state: `btn_create_request_normal.xml`
* pressed state: `btn_create_request_pressed.xml`

#### Color
Все названию цветов должны быть в формате color+{где используется}
 ```diff   
+ Правильно:  `colorDefaultText, colorUserName`

- Неправильно: `colorRed, color_brown`
```

#### Color State List.  Ресурсы должны храниться в папке res/color . 
 ```diff  
+ Примеры хороших названий `colorButtonUserName, colorButtonAction`

- Плохое название: `colorRedSelector, colorButton` т.д
```

#### String

Все строки должны храниться только в ресурсах, даже если это часть какой-то фразы или окончание слова должны начинаться с названия экрана, где они используются и далее через подчеркивание для чего они используются
 ```diff  
+ Правильное название: `about_title`, `userSettings_emailHint`

- Неправильное название `aboutText`, `textEmail`
```

#### Dimensions:
 если dimension используется более чем один раз, то вынесение в ресурсы обязательно. Правила наименования такие же как и для string.
 ```diff  
+ Правильное название: `about_TitleSize`, `userSettings_emailHintSize`

- Неправильное название `dimenAboutText`, `textEmailSize`
```


#### Style 
В стили должны выноситься повторяющиеся атрибуты в однотипных компонентах.

Пример: если у вас на экране >1 одинаковых по виду editText, то нужно создать style и вынести туда все атрибуты с общими значениями

TODO: Найти лучший вариант наименования стилей


#### Menu

Должны быть в формате `menu_{где_используется}`

Пример: `menu_map`, `menu_product_details`. 


Названия id для пунктов menu должны быть в след. формате: `@+id/menu_{назначение}`

Пример: `@+id/menu_copy`, `@+id/menu_edit`

### 1.3  Layouts

| Type   | Class Name            |		Example               |
|--------------| ------------------|-----------------------------|
| Activity   | `MainActivity.java`             | `activity_main.xml`          |
| Fragment       | `MainFragment.java`	            | `fragment_main.xml`    |
| Dialog       | `DatePickerDialog.java`         | `dialog_date_picker.xml`|
| Adapter item |    -      			| `item_contact.xml`  |
| Embeded item | 	-            		| `include_user_view.xml`               |

### 1.4  View's ids

Все имена для компонентов должны начинаться с названий этих компонентов (сокращенных или полных, где это необходимо)+ осмысленное название исходя из назначения в приложении

Вот примеры для самых используемых компонентов


| Component   | Prefix            |		Example               |
|--------------| ------------------|-----------------------------|
| TextView   | `text`             | ` @+id/textName`          |
| EditText       | `edit`	            | `@+id/editAddress`    |
| ImageView       | `image`         | `@+id/imageAvatar`          |
| Button      | `button`        | `@+id/buttonCreateRequest`  |
| RecyclerView         | `recyclerView`	            | `@+id/recyclerViewContacts`               |
| ViewPager         | `viewPager	`           | `@+id/viewPagerCards`     |
| Checkbox         | `checkbox`            | `@+id/checkboxGender`         |
| RadioButton         | `radio`            | `@+id/radioGender`         |
| LinearLayout         | `linear`            | `@+id/linearCardsContainer`         |
| RelativeLayout         | `relative`            | `@+id/relativeCardsContainer`         |
| Toolbar         | `toolbar`            | `@+id/toolbar`         |
| AppBar         | `appbar`            | `@+id/appbar`         |



# License

```
Copyright 2017 Almet-systems Ltd.

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
