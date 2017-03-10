#6 Рекомендуемые решения для наиболее распространенных задач

Если вы не сторонник использования готовых решений и все можете написать сами, то мы очень рады за вас, но вам придется использовать готовые решения, где это возможно для экономии времени в разработке и баг фиксе. Весь эстимейт делается с расчетом на популярные и достаточно надежные готовые решения, если есть таковые. В случае, если у вас нет идей как реализовать ту или иную сложную задачу и вы собираетесь начать писать custom view или custom viewgroup и т.д, то проконсультируйтесь сначала у Team Lead. 

`Для работы с потоками:  RxJava`
Пример реализции:

`Для работы с Rest api: Retrofit 2+ OkHttp+RxJava`
Пример реализации

`Для загрузки картинок: Picasso.`
В том числе для закругленных изображений или круглых изображений https://github.com/vinc3m1/RoundedImageView.  

`Для кастомных кнопок`
https://github.com/medyo/Fancybuttons.

Преимущество библиотеки в том, что она покрывает 99% всех состояний кнопки, которые могут понадобиться и отлично работает с reveal animation для api v21. 

`Проверка разрешений для android 6+`
https://github.com/tbruyelle/RxPermissions 

`Получение фото из камеры или выбор из галереи (рекомендуемое, но не обязательное)`
[https://github.com/miguelbcr/RxPaparazzo]

Если реализовываете свое решение, то не забывать использовать android.support.v4.content.FileProvider

`База данных:  Realm+Rx для новых проектов`
[https://realm.io/docs/java/latest/]

`Подключение кастомных шрифтов:`
[https://github.com/chrisjenx/Calligraphy]

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
