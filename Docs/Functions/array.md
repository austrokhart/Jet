# Functions.Array


## Описание
Класс с методами для работы с массивами.


## Структура

#### Типы класса

```

  type _array_pad_direction = (
    _ARRAY_PAD_LEFT,
    _ARRAY_PAD_RIGHT,
    _ARRAY_PAD_BOTH
  );


  _array_trim_direction = (
    _ARRAY_TRIM_LEFT,
    _ARRAY_TRIM_RIGHT,
    _ARRAY_TRIM_BOTH
  );


  _array_pos_result = (
    _ARRAY_POS_OFFSET = 1,
    _ARRAY_POS_LENGTH = 2
  );


  _array_method_each   = Methods.Functions.Array.Each;
  _array_method_filter = Methods.Functions.Array.Filter;
  _array_method_map    = Methods.Functions.Array.Map;
  _array_method_reduce = Methods.Functions.Array.Reduce;
```  


#### Методы класса

##### Для работы с одним измерением:


* func **array_from**(const \_value: variant): variant[] <br>
  возвращает приведённое к массиву значение \_value
  > если значение \_value:
  > * это массив, возвращается он сам
  > * это nil, возвращается пустой массив
  > * иначе возвращается массив с единственным значением \_value


* func **array_length**(const \_array: variant[]): integer <br>
  возвращает длину массива \_array


* func **array_has_content**(const \_array: variant[]): boolean <br>
  возвращает истину, если массив \_array содержит отличное от нуля количество значений


* func **array_get**(const \_array: variant[]; \_index: integer; \_default_value: variant = nil): variant[] <br>
  возвращает значение элемента массива \_array с индексом \_index, если он установлен, иначе значение \_default_value
  > если индекс \_index отрицательный, индекс считается с конца массива


* proc **array_set**(var \_array: variant[]; \_index: integer; \_value: variant) <br>
  устанавливает в массиве \_array элемент с индексом \_index и значением \_value
  > если индекс \_index отрицательный, индекс считается с конца массива


* proc **array_unset**(var \_array: variant[]; \_index: integer) <br>
  разустанавливает в массиве \_array элемент с индексом \_index, если он установлен
  > если индекс \_index отрицательный, индекс считается с конца массива <br>
  > происходит смещение стоящих впереди индексов


* func **array_is_set**(const \_array: variant[]; \_index: integer): boolean <br>
  возвращает истину, если в массиве \_array установлен элемент с индексом \_index


* proc **array_clear**(var \_array: variant[]) <br>
  разустанавливает все элементы массива \_array


* proc **array_append**(var \_array: variant[]; \_value: variant) <br>
  добавляет в конец массива \_array элемент со значением \_value


* proc **array_prepend**(var \_array: variant[]; \_value: variant) <br>
  добавляет в начало массива \_array элемент со значением \_value
  > происходит смещение стоящих впереди индексов


* proc **array_extend**(var \_array: variant[]; \_value: variant[]) <br>
  добавляет в конец массива \_array последовательность элементов массива \_value


* func **array_pos**(const \_array: variant[]; \_value: variant[]; \_offset: integer = 1): integer[] <br>
  возвращает индекс ближайшего вхождения в массив \_array последовательности элементов подмассива \_value с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>
  > если вхождение подмассива \_value не будет найдено, вернётся значение -1


* func **array_pos_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = 1): integer[] <br>
  возвращает массив с индексом и длиной для ближайшего вхождения в массив \_array последовательности элементов любого подмассива из массива \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>
  > если вхождение ни одного подмассива из \_values не будет найдено, вернётся значение [-1, 0]


* func **array_contains**(const \_array: variant[]; \_value: variant[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если в массив \_array входит последовательность элементов подмассива \_value с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>


* func **array_contains_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = 1): boolean <br>
  возвращает истину, если в массив \_array входит последовательность элементов любого подмассива из массива \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>


* func **array_starts_with**(const \_array: variant[]; \_value: variant[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если массив \_array начинается с последовательности элементов \_value с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>


* func **array_starts_with_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = 1): boolean <br>
  возвращает истину, если массив \_array начинается с последовательности элементов любого подмассива из массива \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>


* func **array_ends_with**(const \_array: variant[]; \_value: variant[]; \_offset: integer = -1): boolean <br>
  возвращает истину, если массив \_array заканчивается на последовательность элементов подмассива \_value с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>


* func **array_ends_with_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = -1): boolean <br>
  возвращает истину, если массив \_array заканчивается на последовательность элементов любого подмассива из массива \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца массива <br>


* func **array_slice**(const \_array: variant[]; \_offset: integer = 1; \_length: variant = nil; \_step: integer = 1): variant[] <br>
  возвращает подмассив от массива \_array с началом в \_offset, длиной \_length и шагом \_step
  > если смещение \_offset отрицательное, начало подмассива будет считаться начиная с конца массива <br>
  > если длина \_length:
  > * равна nil, с учётом смещения длина подмассива будет совпадать с концом массива
  > * отрицательная, длина подмассива будет считаться начиная с конца массива
  >
  > если аргумент \_step отрицательный, элементы будут взяты в обратном порядке


* func **array_splice**(var \_array: variant[]; \_value: variant[]; \_offset: integer = 1; \_length: variant = nil): variant[] <br>
  заменяет в массиве \_array подмассив с началом в \_offset и длиной \_length последовательностью элементов массива \_value и возвращает удалённую последовательность элементов
  > если смещение \_offset отрицательное, начало подмассива будет считаться начиная с конца массива <br>
  > если длина \_length:
  > * равна nil, с учётом смещения длина подмассива будет совпадать с концом массива
  > * отрицательная, длина подмассива будет считаться начиная с конца массива


* func **array_insert**(const \_array: variant[]; \_value: variant[]; \_offset: integer = 1; \_length: variant = nil): variant[] <br>
  заменяет в массиве \_array подмассив с началом в \_offset и длиной \_length массивом \_value и возвращает полученный массив
  > если смещение \_offset отрицательное, начало подмассива будет считаться начиная с конца массива <br>
  > если длина \_length:
  > * равна nil, с учётом смещения длина подмассива будет совпадать с концом массива
  > * отрицательная, длина подмассива будет считаться начиная с конца массива


* func **array_concat**(const \_values: variant[]): variant[] <br>
  возвращает массив из элементов массива \_values
  > элементы массива \_values будут приведены к массивам и склеены


* func **array_repeat**(const \_value: variant[]; \_count: integer): variant[] <br>
  возвращает повторённую \_count раз последовательностью элементов массива \_value


* proc **array_swap**(var \_array: variant[]; \_index, \_other_index: integer) <br>
  обменивает в массиве \_array элементы с индексами \_index и \_other_index


* proc **array_reverse**(const \_array: variant[]) <br>
  устанавливает элементы массива \_array в обратном порядке


* proc **array_pad**(var \_array: variant[]; \_direction: \_array_pad_direction; \_value: variant[]; \_length: integer) <br>
  дополняет массив \_array по краям последовательностью элементов value, в зависимости от направления \_direction, до длины \_length


* proc **array_trim**(var \_array: variant[]; \_direction: \_array_trim_direction; \_value: variant[]) <br>
  очищает массив \_array по краям от последовательности элементов \_value, в зависимости от направления \_direction


* proc **array_trim_any**(var \_array: variant[]; \_direction: \_array_trim_direction; \_values: variant[2]) <br>
  очищает массив \_array по краям от любой последовательности элементов из \_values, в зависимости от направления \_direction


* proc **array_sort**(const \_array: variant[]) <br>
  сортирует массив \_array


* func **array_each**(const \_array: variant[]): \_array_method_each <br>
  возвращает объект класса [Methods.Functions.Array.Each](/Docs/Methods/Functions/Array/each.md) для работы с массивом методом each


* func **array_filter**(const \_array: variant[]): \_array_method_filter <br>
  возвращает объект класса [Methods.Functions.Array.Filter](/Docs/Methods/Functions/Array/filter.md) для работы с массивом методом filter


* func **array_map**(const \_array: variant[]): \_array_method_map <br>
  возвращает объект класса [Methods.Functions.Array.Map](/Docs/Methods/Functions/Array/map.md) для работы с массивом методом map


* func **array_reduce**(const \_array: variant[]): \_array_method_reduce <br>
  возвращает объект класса [Methods.Functions.Array.Reduce](/Docs/Methods/Functions/Array/reduce.md) для работы с массивом методом reduce


* func **array_implode**(const \_array: variant[]; \_separator: string = " "): string <br>
  возвращает строку из значений элементов массива \_array, объединённую значением \_separator


##### Для работы со множеством измерений:

* func **md_array_get**(const \_array: variant[]; \_index: integer; \_path: integer[]; \_default_value: variant = nil): variant[] <br>
  возвращает значение элемента массива \_array с индексом \_index в плоскости \_path, если он установлен, иначе значение \_default_value
  > если аргумент \_index отрицательный, индекс считается с конца


* proc **md_array_set**(var \_array: variant[]; \_index: integer; \_path: integer[] = nil; \_value: variant) <br>
  устанавливает в массиве \_array элемент с индексом \_index в плоскости \_path и значением \_value
  > если аргумент \_index отрицательный, индекс считается с конца


* proc **md_array_unset**(var \_array: variant[]; \_index: integer; \_path: integer[] = nil) <br>
  разустанавливает в массиве \_array элемент с индексом \_index в плоскости \_path, если он установлен
  > если аргумент \_index отрицательный, индекс считается с конца
  > происходит смещение стоящих впереди индексов


* func **md_array_is_set**(const \_array: variant[]; \_index: integer; \_path: integer[] = nil): boolean <br>
  возвращает истину, если в массиве \_array установлен элемент с индексом \_index в плоскости \_path


* func **md_array_pos**(const \_array: variant[]; \_path: integer[] = nil; \_value: variant[]; \_offset: integer = 1): integer <br>
  возвращает индекс ближайшего вхождения в массив \_array последовательности элементов подмассива \_value в плоскости \_path с учётом смещения \_offset


* func **md_array_pos_any**(const \_array: variant[]; \_path: integer[] = nil; \_values: variant[2]; \_offset: integer = 1): integer[] <br>
  возвращает массив с индексом и длиной для ближайшего вхождения в массив \_array последовательности элементов любого подмассива из массива \_values в плоскости \_path с учётом смещения \_offset


* func **md_array_contains**(const \_array: variant[]; \_path: integer[] = nil; \_value: variant[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если в массиве \_array встречается последовательность элементов подмассива \_value в плоскости \_path с учётом смещения \_offset


* func **md_array_contains_any**(const \_array: variant[]; \_path: integer[] = nil; \_value: variant[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если в массиве \_array встречается последовательность элементов любого подмассива из массива \_values в плоскости \_path с учётом смещения \_offset


* func **md_array_starts_with**(const \_array: variant[]; \_path: integer[] = nil; \_value: variant[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если массив \_array начинается с последовательности элементов \_value в плоскости \_path с учётом смещения \_offset


* func **md_array_starts_with_any**(const \_array: variant[]; \_path: integer[] = nil; \_values: variant[2]; \_offset: integer = 1): boolean <br>
  возвращает истину, если массив \_array начинается с последовательности элементов любого подмассива из массива \_values в плоскости \_path с учётом смещения \_offset


* func **md_array_ends_with**(const \_array: variant[]; \_path: integer[] = nil; \_value: variant[]; \_offset: integer = -1): boolean <br>
  возвращает истину, если массив \_array заканчивается на последовательность элементов подмассива \_value в плоскости \_path с учётом смещения \_offset


* func **md_array_ends_with_any**(const \_array: variant[]; \_path: integer[] = nil; \_values: variant[2]; \_offset: integer = -1): boolean <br>
  возвращает истину, если массив \_array заканчивается на последовательность элементов любого подмассива из массива \_values в плоскости \_path с учётом смещения \_offset


* func **md_array_slice**(const \_array: variant[]; \_path: integer[] = nil; \_offset: integer = 1; \_length: variant = nil; \_step: integer = 1): variant[] <br>
  возвращает срез массива \_array с началом в \_offset, длиной \_length и шагом \_step в плоскости \_path
  > если аргумент \_offset отрицательный, начало среза будет считаться начиная с конца массива <br>
  > если аргумент \_length:
  > * равен nil, с учётом смещения длина среза будет совпадать с концом массива
  > * отрицательный, длина среза будет считаться начиная с конца массива
  >
  > если аргумент \_step отрицательный, элементы среза будут взяты в обратном порядке


* proc **md_array_sort**(const \_array: variant[]; \_path: integer[] = nil) <br>
  сортирует массив \_array, используя значения элементов в плоскости \_path
