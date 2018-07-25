# Methods.Functions.Array.Map


## Описание

Класс для работы с массивом методом map, является наследником [Methods.Functions.Array.BaseIterable](/Docs/Methods/Functions/Array/base_iterable.md). Позволяет преобразовать значения массива по определённому выражению.


## Структура

#### Методы класса


* **new**(\_array: variant[]): Methods.Functions.Array.Filter <br>
  возвращает иниациализированный объект текущего класса


#### Свойства объекта


* var **\__result**: variant[] <br>
  хранит результат выполнения


#### Методы объекта


* proc **\__apply**(\_value: boolean) <br>
  записывает значение \_value в результат


* proc **\__assign**(var \_variable: variant; \_value: variant = nil) <br>
  записывает результат в переменную \_variable, если значение \_value идентично nil, иначе значение \__value


## Примеры использования

Позволяет перебрать все значения массива и получить массив квадратов значений:

```

var numbers: integer[];

numbers = [10, 20, 30, 40, 50];

with Methods.Functions.Array.Map.new(numbers) do
  while __next
    __apply(__item *__item);
  end;

  __assign(numbers); -- после этого значение numbers будет равно [100, 400, 900, 1600, 2500]
end;
```

То же самое с использованием функции array_map:

```

var numbers: integer[];

numbers = [10, 20, 30, 40, 50];

with array_map(numbers) do
  while __next
    __apply(__item *__item);
  end;

  __assign(numbers); -- после этого значение numbers будет равно [100, 400, 900, 1600, 2500]
end;
```
