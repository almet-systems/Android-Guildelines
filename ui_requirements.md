#4 Требования по реализации UI в приложении


* __Требования действуют для всех проектов по умолчанию__.
* __Требования не действуют только если они противоречат желаниями заказчика по конкретному экрану/проекту__




1. Все кликабельные элементы должны иметь pressed state, который будет явно показывать пользователю, что данный элемент кликабелен.

 *  Для кнопок с непрозрачным background это затемнение или осветление background при нажатии. Для api <21 - просто изменяется цвет на более темный или светлый, для api>21 обязательно использование reveal animation

 * Для кнопок с прозрачным background могут использоваться стандартные стейты.

  Прямоугольный
  ```xml
  android:background="?selectableItemBackground"
  ```

  Овальный
  ```xml
  android:background="?selectableItemBackgroundBorderless"
  ```

2. Состояния экранов

 * Если данные появляются только после загрузки их по сети, то обязательно наличие состояния загрузки

 * Если на экране данных может не быть, то он  должен иметь состояние для этого, которое будет показывать сообщение о том, что данных к показу нет

 * Если на экране возможна ошибка загрузки данных в результате отсутствия интернета, то показывать состояние с текстом, что именно пошло не так и кнопкой по нажатию на которую данные начинают обновляться

 * Если данные отображаются и предполагается, что они могут устареть за небольшой период времени (новости, постоянно обновляемый контент), то обязательно использовать `SwipeRefreshLayout` для обновления данных

3. Для картинок обязательно наличие placeholder на время загрузки и в случае неудачной загрузки изображения, чтобы пользователь понимал, что в данном месте должна быть картинка, но она не загрузилась. 

4. Все анимации должны иметь `Interpolator` отличный от `LinearInterpolator` т.е должны происходить с положительным или отрицательным ускорением. 

5. Если часть текста отличается стилем/цветом/размером в пределах одной фразы или строки, то использовать `SpannableString` и не делать несколько `TextView`

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
