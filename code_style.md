# 2 Код стайл

## 2.1 правила по Java коду 

### 2.2.1 Аргумента в Fragments и Activities

Когда данные передаются в `Activity` или `Fragment` через `Intent` или `Bundle`, вы __должны__ создать `public static` метод, который обеспечивает создание подходящего `Fragment` или `Intent`. 


В случае `Activity` этот метод называется `getStartIntent()`:

```java
public static Intent getStartIntent(Context context, User user) {
	Intent intent = new Intent(context, ThisActivity.class);
	intent.putParcelableExtra(EXTRA_USER, user);
	return intent;
}
```

Для `Fragment` он называется `newInstance()`:

```java
public static UserFragment newInstance(User user) {
	UserFragment fragment = new UserFragment;
	Bundle args = new Bundle();
	args.putParcelable(ARGUMENT_USER, user);
	fragment.setArguments(args)
	return fragment;
}
```

__Важно__: Эти методы должны быть объявлены до метода `onCreate()`.


## 2.2 XML правила

### 2.2.1 Используйте "self closing tags"

Когда XML элемент не содержит никакого контента, вы __должны__ использовать "self closing tags". 

Пример:

Правильно

```xml
<TextView
	android:id="@+id/textPofile"
	android:layout_width="wrap_content"
	android:layout_height="wrap_content" />
```

__Неправильно__ :

```xml
<!-- Не делайте этого! -->
<TextView
    android:id="@+id/textProfile"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" >
</TextView>
```

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
