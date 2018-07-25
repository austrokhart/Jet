# Methods.Functions.Array.Reduce


## Описание

Класс для работы с массивом методом reduce, является наследником [Methods.Functions.Array.BaseIterable](/Docs/Methods/Functions/Array/base_iterable.md). Позволяет сократить значения массива к одному значению по определённому выражению.


## Структура

#### Методы класса


* **new**(\_array: variant[]; \_initial_value: variant): Methods.Functions.Array.Filter <br>
  возвращает иниациализированный объект текущего класса
  > для корректного сокращения необходимо объявить начальное значение


#### Свойства объекта


* var **\__result**: variant[] <br>
  хранит результат выполнения


#### Методы объекта


* proc **\__apply**(\_value: boolean) <br>
  записывает значение \_value в результат


* proc **\__assign**(var \_variable: variant; \_value: variant = nil) <br>
  записывает результат в переменную \_variable, если значение \_value идентично nil, иначе значение \__value


## Примеры использования

Позволяет перебрать все значения массива и сократить их до произведения:

```

var numbers: integer[];
var mult: integer;

numbers = [10, 20, 30, 40, 50];

with Methods.Functions.Array.Reduce.new(numbers, 1) do
  while __next
    __apply(__result *__item);
  end;

  __assign(mult); -- после этого значение mult будет равно 12КК
end;
```

То же самое с использованием функции array_map:

```

var numbers: integer[];
var mult: integer;

numbers = [10, 20, 30, 40, 50];

with array_reduce(numbers, 1) do
  while __next
    __apply(__result *__item);
  end;

  __assign(mult); -- после этого значение mult будет равно 12КК
end;
```
