# Functions.Variable


## Описание

Класс с методами для работы с переменными.


## Структура

#### Типы класса

```

  type _var_type = (
    _TYPE_STRING  = 1,
    _TYPE_INTEGER = 2,
    _TYPE_REAL    = 3,
    _TYPE_BOOLEAN = 4,
    _TYPE_DATE    = 5,
    _TYPE_OBJECT  = 6,
    _TYPE_VARIANT = 7,
    _TYPE_ARRAY   = 8,
    _TYPE_CLASS   = 9,
    _TYPE_NIL     = 10
  );
```

#### Методы класса

* func **var_to_int**(const \_value: variant): integer <br>
  возвращает приведённое к типу integer значение \_value


* func **var_to_real**(const \_value: variant): real <br>
  возвращает приведённое к типу real значение \_value


* func **var_to_str**(const \_value: variant): string <br>
  возвращает приведённое к типу string значение \_value


* func **var_to_dump**(const \_value: variant): string <br>
  возвращает приведённое к подробному строковому виду значение \_value


* func **var_is_string**(const \_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу string


* func **var_is_integer**(const \_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу integer


* func **var_is_real**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу real


* func **var_is_number**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу number


* func **var_is_boolean**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу boolean


* func **var_is_date**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу date


* func **var_is_object**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу object


* func **var_is_variant**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу variant


* func **var_is_array**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу array


* func **var_is_class**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу class


* func **var_is_nil**(\_value: variant): boolean <br>
  возвращает истину, если значение \_value принадлежит типу nil


* func **var_equal**(const \_value, \_other_value: variant): boolean <br>
  возвращает истину, если значения \_value и \_other_value равны


* func **var_not_equal**(const \_value, \_other_value: variant): boolean <br>
  возвращает истину, если значения \_value и \_other_value не равны


* func **var_identical**(\_value, \_other_value: variant): boolean <br>
  возвращает истину, если значения и типы \_value и \_other_value равны


* func **var_not_identical**(\_value, \_other_value: variant): boolean <br>
  возвращает истину, если значения и типы \_value и \_other_value не равны


* func **var_type_is**(\_value: variant; \_expected: \_var_type): boolean <br>
  возвращает истину, если значение \_value принадлежит типу \_expected


* func **var_class_is**(\_value: variant; \_expected: class): boolean <br>
  возвращает истину, если значение \_value принадлежит классу \_expected


* func **var_instance_of**(\_value: variant; \_expected: class): boolean <br>
  возвращает истину, если \_value является объектом класса \_expected


* proc **var_swap**(var \_variable: variant; var \_other_variable: variant) <br>
  обменивает значения переменных
