# Jet
Библиотека, предоставляющая базовые средства для работы с кодом и данными.

## Описание


В данной библиотеке реализовано множество вспомогательных методов для работы с данными, в том числе с:

* [числами](/Docs/Functions/math.md),
* [переменными](/Docs/Functions/variable.md),
* [классами](/Docs/Functions/class.md),
* [объектами](/Docs/Functions/object.md),
* [строками](/Docs/Functions/string.md),
* [датами](/Docs/Functions/date.md),
* [массивами](/Docs/Functions/array.md).

Стоит обратить внимание на [методы для двусторонней конвертации дат в формат ISO 8601](/Docs/Functions/date_iso.md).


Также в библиотеке реализовано множество вспомогательных классов. Стоит обратить внимание на:

* класс [Dict](/Docs/dict.md), который является реализацией словаря или ассоциативного массива,

* класс [Escaper](/Docs/escaper.md), который позволяет экранировать и разэкранировать строки с учётом управляющих последовательностей и Unicode,

* класс [JSON](/Docs/json.md), который повзоляет проводить двустороннюю конвертацию данных Турбо в формат JSON,

* класс [SmartConsole](/Docs/smart_console.md), который предоставляет расширенное управление консолью, в том числе её использование в серверных классах.


Для поддержания проекта в актуальном состоянии реализованы [классы для модульного тестирования](/Docs/UnitTesting/main.md), которые также можно использовать для тестирования других проектов.

## Подключение

Любой набор методов можно подключить, используя:
```
  import Jet classes Functions.<имя_набора>;
```

Любой класс можно подключить, используя:
```
  import Jet classes Packages.<имя_класса>;
```

## Структура

#### Методы

* [Functions.Math](/Docs/Functions/math.md) <br>
  методы для работы с числами

* [Functions.Variable](/Docs/Functions/variable.md) <br>
  методы для работы с переменными

* [Functions.Class](/Docs/Functions/class.md) <br>
  методы для работы с классами

* [Functions.Object](/Docs/Functions/object.md) <br>
  методы для работы с объектами

* [Functions.String](/Docs/Functions/string.md) <br>
  методы для работы со строками

* [Functions.Date](/Docs/Functions/date.md) <br>
  методы для работы с датами

* [Functions.DateISO](/Docs/Functions/date_iso.md) <br>
  методы для работы с датами в формате ISO 8601

* [Functions.Array](/Docs/Functions/array.md) <br>
  методы для работы с массивами


### Классы:

* Packages.Iterator <br>
  класс для итерации

* Packages.Dict <br>
  класс для работы со словарями (аналог ассоциативных массивов)

* Packages.Escaper <br>
  класс для работы с экранированием строк

* Packages.JSON <br>
  функции для работы с форматом JSON

* Packages.SmartConsole <br>
  класс для работы с консолью

* Packages.Timer <br>
  класс для измерения времени
