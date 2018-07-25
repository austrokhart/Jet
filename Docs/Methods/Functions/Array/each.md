# Methods.Functions.Array.Each


## Описание

Класс для работы с массивом методом each, является наследником [Methods.Functions.Array.BaseIterable](/Docs/Methods/Functions/Array/base_iterable.md). Позволяет перебрать все значения массива.


## Структура

#### Методы класса


* **new**(\_array: variant[]): Methods.Functions.Array.Each <br>
  возвращает иниациализированный объект класса


## Примеры использования

Позволяет перебрать значения массива и вывести в консоль их произведения на 2:

```

with Methods.Functions.Array.Each.new([10, 20, 30, 40, 50]) do
  while __next
    trace(__item *2);
  end;
end;
```

То же самое с использованием функции array_each:

```

with array_each([10, 20, 30, 40, 50]) do
  while __next
    trace(__item *2);
  end;
end;
```
