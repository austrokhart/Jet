# Functions.Array

## Структура

### Процедуры и функции для работы с одним измерением:
<br>


* func **array_from**(const \_value: variant): variant[] <br>
  возвращает приведённое к массиву значение \_value
  > если аргумент \_value:
  > * это массив, возвращается он сам
  > * это nil, возвращается пустой массив
  > * иначе возвращается массив с единственным значением \_value


* func **array_length**(const \_array: variant[]): integer <br>
  возвращает длину массива \_array


* func **array_has_content**(const \_array: variant[]): boolean <br>
  возвращает истину, если массив \_array содержит отличное от нуля количество значений


* func **array_get**(const \_array: variant[]; \_index: integer; \_default_value: variant = nil): variant[] <br>
  возвращает значение элемента массива \_array с индексом \_index, если он установлен, иначе значение \_default_value
  > если аргумент \_index отрицательный, индекс считается с конца


* proc **array_set**(var \_array: variant[]; \_index: integer; \_value: variant) <br>
  устанавливает в массиве \_array элемент с индексом \_index и значением \_value
  > если аргумент \_index отрицательный, индекс считается с конца


* proc **array_unset**(var \_array: variant[]; \_index: integer) <br>
  разустанавливает в массиве \_array элемент с индексом \_index, если он установлен
  > если аргумент \_index отрицательный, индекс считается с конца
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


* func **array_pos_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = 1): integer[] <br>
  возвращает массив с индексом и длиной для ближайшего вхождения в массив \_array последовательности элементов любого подмассива из массива \_values с учётом смещения \_offset


* func **array_contains**(const \_array: variant[]; \_value: variant[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если в массиве \_array встречается последовательность элементов подмассива \_value с учётом смещения \_offset


* func **array_contains_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = 1): boolean <br>
  возвращает истину, если в массиве \_array встречается последовательность элементов любого подмассива из массива \_values с учётом смещения \_offset


* func **array_starts_with**(const \_array: variant[]; \_value: variant[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если массив \_array начинается с последовательности элементов \_value с учётом смещения \_offset


* func **array_starts_with_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = 1): boolean <br>
  возвращает истину, если массив \_array начинается с последовательности элементов любого подмассива из массива \_values с учётом смещения \_offset


* func **array_ends_with**(const \_array: variant[]; \_value: variant[]; \_offset: integer = -1): boolean <br>
  возвращает истину, если массив \_array заканчивается на последовательность элементов подмассива \_value с учётом смещения \_offset


* func **array_ends_with_any**(const \_array: variant[]; \_values: variant[2]; \_offset: integer = -1): boolean <br>
  возвращает истину, если массив \_array заканчивается на последовательность элементов любого подмассива из массива \_values с учётом смещения \_offset


* func **array_slice**(const \_array: variant[]; \_offset: integer = 1; \_length: variant = nil; \_step: integer = 1): variant[] <br>
  возвращает срез массива \_array с началом в \_offset, длиной \_length и шагом \_step
  > если аргумент \_offset отрицательный, начало среза будет считаться начиная с конца массива <br>
  > если аргумент \_length:
  > * равен nil, с учётом смещения длина среза будет совпадать с концом массива
  > * отрицательный, длина среза будет считаться начиная с конца массива
  >
  > если аргумент \_step отрицательный, элементы среза будут взяты в обратном порядке


* func **array_splice**(var \_array: variant[]; \_value: variant[]; \_offset: integer = 1; \_length: variant = nil): variant[] <br>
  заменяет подмассив с началом в \_offset и длиной \_length последовательностью элементов массива \_value и возвращает удалённую последовательность элементов
  > значение \_value будет приведено к массиву
  > если смещение \_offset отрицательное, начало подмассива будет считаться с конца массива <br>
  > если длина \_length:
  > * равна nil, конец подмассива будет соответствовать концу массива
  > * отрицательная, конец подмассива будет считаться с конца массива


* func **array_insert**(const \_array: variant[]; \_value: variant[]; \_offset: integer = 1; \_length: variant = nil): variant[] <br>
  заменяет подмассив с началом в \_offset и длиной \_length массивом \_value и возвращает полученный массив


* func **array_concat**(const \_values: variant[]): variant[] <br>
  возвращает массив из элементов массива \_values
  > элементы массива \_values будут приведены к массивам и склеены


* func **array_repeat**(const \_value: variant[]; \_count: integer): variant[] <br>
  возвращает массив с последовательностью элементов массива \_value, повторяющейся \_count раз


* proc **array_swap**(var \_array: variant[]; \_index, \_other_index: integer) <br>
  обменивает в массиве \_array элементы с индексами \_index и \_other_index


* proc **array_reverse**(const \_array: variant[]) <br>
  устанавливает элементы массива \_array в обратном порядке


* proc **array_pad**(var \_array: variant[]; \_direction: \_array_pad_direction; \_value: variant[]; \_length: integer) <br>
  дополняет массив \_array последовательностью элементов массива value по краям, в зависимости от направления \_direction, до длины \_length


* proc **array_trim**(var \_array: variant[]; \_direction: \_array_trim_direction; \_value: variant[]) <br>
  очищает массив \_array от последовательности элементов массива \_value по краям, в зависимости от направления \_direction


* proc **array_trim_any**(var \_array: variant[]; \_direction: \_array_trim_direction; \_values: variant[2]) <br>
  очищает массив \_array от последовательностей элементов любого массива из \_values по краям, в зависимости от направления \_direction


* proc **array_sort**(const \_array: variant[]) <br>
  сортирует массив \_array


* func **array_each**(const \_array: variant[]): \_array_method_each <br>
  возвращает соответствующий объект класса-обёртки для работы с массивом методом each


* func **array_filter**(const \_array: variant[]): \_array_method_filter <br>
  возвращает соответствующий объект класса-обёртки для работы с массивом методом filter


* func **array_map**(const \_array: variant[]): \_array_method_map <br>
  возвращает соответствующий объект класса-обёртки для работы с массивом методом map


* func **array_reduce**(const \_array: variant[]): \_array_method_reduce <br>
  возвращает соответствующий объект класса-обёртки для работы с массивом методом reduce


* func **array_implode**(const \_array: variant[]; \_separator: string = " "): string <br>
  возвращает строку из значений элементов массива \_array, объединённую значением \_separator

### Процедуры и функции для работы со множеством измерений:
<br>


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
