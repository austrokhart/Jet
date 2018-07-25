# Functions.String

## Структура

### Типы
<br>


    _str_pad_direction = (
      _STR_PAD_LEFT,
      _STR_PAD_RIGHT,
      _STR_PAD_BOTH
    );


    _str_trim_direction = (
      _STR_TRIM_LEFT,
      _STR_TRIM_RIGHT,
      _STR_TRIM_BOTH
    );


    _str_pos_result = (
      _STR_POS_OFFSET = 1,
      _STR_POS_LENGTH = 2
    );


    _str_method_find = Methods.Functions.String.Find;   

### Свойства
<br>


    _STR_PAD_LEFT:  _str_pad_direction;
    _STR_PAD_RIGHT: _str_pad_direction;
    _STR_PAD_BOTH:  _str_pad_direction;


    _STR_TRIM_LEFT:  _str_trim_direction;
    _STR_TRIM_RIGHT: _str_trim_direction;
    _STR_TRIM_BOTH:  _str_trim_direction;


    _STR_POS_OFFSET: str_pos_result = 1;
    _STR_POS_LENGTH: str_pos_result = 2;

### Процедуры и функции:
<br>


* func **str_from**(const \_value: variant): string <br>
  возвращает приведённое к строке значение \_value


* func **str_length**(const \_string: string): integer <br>
  возвращает длину строки \_string


* func **str_has_content**(const \_string: string): boolean <br>
  возвращает истину, если строка \_string содержит отличное от нуля количество символов


* func **str_char_is_set**(const \_string: string; \_index: integer): boolean <br>
  возвращает истину, если в строке \_string установлен символ с индексом \_index


* func **str_char**(const \_string: string; \_index: integer; \_default_value: string): string <br>
  возвращает символ в строке \_string с индексом \_index, если он установлен, иначе значение \_default_value
  > если индекс \_index отрицательный, индекс считается с конца строки


* func **str_substr**(const \_string: string; \_offset: integer = 1; \_length: variant = nil; \_step: integer = 1): string <br>
  возвращает подстроку от строки \_string с началом в \_offset, длиной \_length и шагом \_step
  > если смещение \_offset отрицательное, начало подстроки будет считаться начиная с конца массива <br>
  > если длина \_length:
  > * равна nil, с учётом смещения длина подстроки будет совпадать с концом строки
  > * отрицательная, длина подстроки будет считаться начиная с конца строки
  >
  > если аргумент \_step отрицательный, символы будут взяты в обратном порядке


* func **str_pos**(const \_string: string; \_value: string; \_offset: integer = 1): integer <br>
  возвращает индекс ближайшего вхождения подстроки \_value в строку \_string с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки
  > если вхождение подстроки не будет найдено, вернётся значение -1


* func **str_pos_any**(const \_string: string; \_values: string[]; \_offset: integer = 1): integer[] <br>
  возвращает индекс и длину для ближайшего вхождения любой подстроки из \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки <br>
  > если вхождение ни одной подстроки не будет найдено, вернётся значение [-1, 0]


* func **str_contains**(const \_string: string; \_value: string; \_offset: integer = 1): boolean <br>
  возвращает истину, если в строку \_string входит подстрока \_value с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки


* func **str_contains_any**(const \_string: string; \_values: string[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если в строку \_string входит любая подстрока из \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки


* func **str_starts_with**(const \_string: string; \_value: string; \_offset: integer = 1): boolean <br>
  возвращает истину, если строка \_string начинается с подстроки \_value с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки


* func **str_starts_with_any**(const \_string: string; \_values: string[]; \_offset: integer = 1): boolean <br>
  возвращает истину, если строка \_string начинается с любой подстроки из \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки


* func **str_ends_with**(const \_string: string; \_value: string; \_offset: integer = -1): boolean <br>
  возвращает истину, если строка \_string заканчивается на подстроку \_value с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки


* func **str_ends_with_any**(const \_string: string; \_values: string[]; \_offset: integer = -1): boolean <br>
  возвращает истину, если строка \_string заканчивается на любую подстроку из \_values с учётом смещения \_offset
  > если смещение \_offset отрицательное, смещение считается с конца строки


* func **str_find**(const \_string: string; \_value: string): \_str_method_find <br>
  возвращает объект соответствующего класса-обёртки для поиска подстрок и работы с ними


* func **str_find_any**(const \_string: string; \_values: string[]): \_str_method_find <br>
  возвращает объект соответствующего класса-обёртки для поиска подстрок и работы с ними


* func **str_repeat**(const \_string: string; \_count: integer): string <br>
  возвращает повторённую \_count раз строку \_string


* func **str_pad**(const \_string: string; \_direction: \_str_pad_direction; \_value: string; \_length: integer): string <br>
  возвращает строку \_string, дополненную по краям последовательностью символов \_value, в зависимости от аргумента \_direction, до длины \_length


* func **str_trim**(const \_string: string; \_direction: str_trim_direction; \_value: string): string <br>
  возвращает строку \_string, очищенную по краям от последовательности символов \_value, в зависимости от направления \_direction


* func **str_trim_any**(const \_string: string; \_direction: str_trim_direction; \_values: string[]): string <br>
  возвращает строку \_string, очищенную по краям от любой последовательности символов из массива \_values, в зависимости от направления \_direction


* func **str_splice**(var \_string: string; \_value: string; \_offset: integer; \_length: variant = nil): string <br>
  заменяет в строке \_string подстроку с началом в \_offset и длиной \_length строкой \_value и возвращает удалённую последовательность символов
  > если смещение \_offset отрицательное, начало подстроки будет считаться начиная с конца строки <br>
  > если длина \_length:
  > * равна nil, с учётом смещения длина подстроки будет совпадать с концом строки
  > * отрицательная, длина подстроки будет считаться начиная с конца строки


* func **str_insert**(const \_string: string; \_value: string; \_offset: integer = 1; \_length: variant = nil): string <br>
  заменяет в строке \_string подстроку с началом в \_offset и длиной \_length строкой \_value и возвращает полученную строку
  > если смещение \_offset отрицательное, начало подстроки будет считаться начиная с конца строки <br>
  > если длина \_length:
  > * равна nil, с учётом смещения длина подстроки будет совпадать с концом строки
  > * отрицательная, длина подстроки будет считаться начиная с конца строки


* func **str_replace**(const \_string: string; \_value: string; \_replacement: string): string <br>
  возвращает строку \_string с заменой встречающихся последовательностей \_value на значение \_replacement


* func **str_replace_any**(const \_string: string; \_values: string[]; \_replacement: string): string <br>
  возвращает строку \_string с заменой любых встречающихся последовательностей из values на значение \_replacement


* func **str_format**(const \_string: string; \_value: variant): string <br>
  возвращает строку \_string с применением форматирования
  > значение \_value будет приведено к массиву <br>
  > в результате форматирования последовательности "{}" будут заменены на соответствующие значения из массива значений value <br>
  > чтобы использовать в строке последовательность "{}", её нужно удвоить до "{{}}" <br>
  > чтобы использовать в строке последовательность "{замена}", её нужно обернуть до "{{{}}}"


* func **str_explode**(const \_string: string; \_separator: string): string[] <br>
  возвращает массив подстрок, полученных при разбиении строки \_string по значению \_separator


* func **str_explode_any**(const \_string: string; \_separators: string[]): string[] <br>
  возвращает массив подстрок, полученных при разбиении строки \_string по любому значению из \_separators
