# Functions.ArrayObject

## Структура
Структура класса:


* **func** array_from(value: variant = nil): variant[] <br>
  возвращает приведённое к массиву значение value
  > если аргумент value:
  > * это массив, возвращается он сам
  > * это объект ArrayObject, возвращается его содержимое
  > * равен nil, возвращается пустой массив
  > * иначе возвращается массив со значением value


* **func** array_from_iterable(value: object): variant[] <br>
  возвращает массив, заполненный элементами объекта value
  > value должен быть объектом класса, имеющего свойства count и items, например List


* **func** array_length(array: variant[]): integer <br>
  возвращает длину массива array


* **func** array_has_content(array: variant[]): boolean <br>
  возвращает истину, если массив array не является пустым


* **func** array_get(array: variant[]; index: integer; path: integer[] = nil; default_value: variant = nil): variant[] <br>
  возвращает значение элемента массива array с индексом index в плоскости path, если он установлен, иначе значение default_value
  > в случае отрицательного аргумента index индекс считается с конца


* **proc** array_set(var array: variant[]; index: integer; value: variant; path: integer[] = nil) <br>
  устанавливает в массиве array элемент с индексом index и значением value в плоскости path
  > в случае отрицательного аргумента index индекс считается с конца


* **proc** array_unset(var array: variant[]; index: integer; path: integer[] = nil) <br>
  разустанавливает в массиве array элемент с индексом index в плоскости path, если он установлен
  > если плоскость не задана, происходит смещение стоящих впереди индексов


* **func** array_is_set(array: variant[]; index: integer; path: integer[] = nil): boolean <br>
  возвращает истину, если в массиве array задан элемент с индексом index в плоскости path


* **proc** array_clear(var array: variant[]; path: integer[] = nil) <br>
  разустанавливает все элементы массива array в плоскости path


* **proc** array_append(var array: variant[]; value: variant) <br>
  добавляет в конец массива array элемент со значением value


* **proc** array_prepend(var array: variant[]; value: variant) <br>
  добавляет в начало массива array элемент со значением value


* **proc** array_extend(var array: variant[]; value: variant[]) <br>
  добавляет в конец массива array элементы массива value


* **func** array_pos(array: variant[]; value: variant[]; path: integer[] = nil; offset: integer = 1): integer[] <br>
  пару <индекс вхождения, длина вхождения> для ближайшего вхождения в массив array последовательности элементов value в плоскости path


* **func** array_contains(array: variant[]; value: variant; path: integer[] = nil; offset: integer = 1): boolean <br>
  возвращает истину, если в массиве array встречается любой из элементов value в плоскости path


* **func** array_slice(array: variant[]; offset: integer = 1; length: variant = nil; path: integer[] = nil): variant[] <br>
  возвращает срез массива array с началом в offset и длиной length в плоскости path
  > если аргумент offset отрицательный, начало среза будет считаться с конца массива <br>
  > если аргумент length:
  > * равен nil, конец среза будет соответствовать концу массива
  > * отрицательный, длина среза будет считаться с конца строки


* **func** array_splice(var array: variant[]; value: variant; offset: integer; length: variant = nil): variant[] <br>
  заменяет подмассив с началом в offset и длиной length элементами value и возвращает удалённый подмассив
  > значение value будет приведено к массиву
  > если смещение offset отрицательное, начало подмассива будет считаться с конца массива <br>
  > если длина length:
  > * равна nil, конец подмассива будет соответствовать концу массива
  > * отрицательная, конец подмассива будет считаться с конца массива


* **func** array_concat(values: variant[]): variant[] <br>
  возвращает массив, расширенный элементами массива values
  > элементы массива values будут приведены к массивам


* **func** array_repeat(value: variant[]; count: integer): variant[] <br>
  возвращает массив с элементами value, повторяющимися count раз
  > значение value будет приведено к массиву


* **proc** array_swap(var array: variant[]; index, other_index: integer; path: integer[] = nil) <br>
  обменивает в массиве array элементы с индексами index и other_index в плоскости path, если они установлены


* **proc** array_reverse(array: variant[]) <br>
  располагает элементы массива array в обратном порядке


<!-- - **proc** array_pad(array: variant[]; direction: array_pad_direction; value: variant[]; length: integer) <br>
  дополняет массив array элементами value по краям до длины length
  > агрумент value будет приведён к массиву -->


<!-- - **proc** array_trim(array: variant[]; path: integer[] = nil; direction: array_trim_direction; value: variant) <br>
  очищает массив array от любого из элементов value по краям
  > агрумент value будет приведён к массиву -->


* **proc** array_sort(array: variant[]; path: integer[] = nil) <br>
  сортирует массив array, используя значения в плоскости path


* **func** array_each(array: variant[]; path: integer[] = nil): array_method_each <br>
  возвращает объект класса-обёртки для работы с массивом


* **func** array_filter(array: variant[]; path: integer[] = nil): array_method_filter <br>
  возвращает объект класса-обёртки для работы с массивом


* **func** array_map(array: variant[]; path: integer[] = nil): array_method_map <br>
  возвращает объект класса-обёртки для работы с массивом


* **func** array_reduce(array: variant[]; path: integer[] = nil): array_method_reduce <br>
  возвращает объект класса-обёртки для работы с массивом


- **func** array_implode(array: variant[]; separator: string = " "; path: integer[] = nil): string <br>
  возвращает строку из значений элементов массива array в плоскости path, объединённую значением separator
