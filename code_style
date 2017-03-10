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

