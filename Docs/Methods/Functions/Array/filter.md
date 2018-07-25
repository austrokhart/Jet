# Methods.Functions.Array.Filter


## Описание

Класс для работы с массивом методом filter, является наследником [Methods.Functions.Array.BaseIterable](/Docs/Methods/Functions/Array/base_iterable.md). Позволяет отфильтровать значения массива по определённому выражению.


## Структура

#### Методы класса


* **new**(\_array: variant[]): Methods.Functions.Array.Filter <br>
  возвращает иниациализированный объект текущего класса


#### Свойства объекта


* var **\__result**: variant[] <br>
  хранит результат выполнения


#### Методы объекта


* proc **\__apply**(\_value: boolean) <br>
  записывает текущий элемент в результат, если значение \_value истинно


* proc **\__assign**(var \_variable: variant; \_value: variant = nil) <br>
  записывает результат в переменную \_variable, если значение \_value идентично nil, иначе значение \__value


## Примеры использования

Позволяет перебрать все значения массива и получить массив нечётных значений (отфильтровать чётные):

```

var numbers: integer[];

numbers = [11, 22, 33, 44, 55];

with Methods.Functions.Array.Filter.new(numbers) do
  while __next
    __apply(mod(__item, 2) = 0);
  end;

  __assign(numbers); -- после этого значение numbers будет равно [11, 33, 55]
end;
```

То же самое с использованием функции array_filter:

```

var numbers: integer[];

numbers = [11, 22, 33, 44, 55];

with array_filter(numbers) do
  while __next
    __apply(mod(__item, 2) = 0);
  end;

  __assign(numbers); -- после этого значение numbers будет равно [11, 33, 55]
end;
```
