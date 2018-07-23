# Functions.String

## Структура
Структура класса:


* func *str_from(value: variant): string* <br>
  возвращает значение value, приведённое к строке


* func *str_length(str: string): integer* <br>
  возвращает длину строки str


* func *str_has_content(str: string): boolean* <br>
  возвращает истину, если строка str не является пустой


* func *str_char_at(str: string; index: integer): string* <br>
  возвращает символ в строке str по индексу index, если индекс находится в пределах строки, иначе пустую строку


* func *str_substr(str: string; offset: integer = 1; length: variant = nil): string* <br>
  возвращает подстроку с началом в offset и длиной length
  > если смещение offset отрицательное, начало подстроки будет считаться с конца строки <br>
  > если длина length:
  > * равна 1, конец подстроки будет соответствовать концу строки
  > * отрицательная, конец подстроки будет считаться с конца строки


* func *str_pos(str: string; value: variant; offset: integer = 1): integer[]* <br>
  возвращает пару <индекс вхождения, длина вхождения> для ближайшего вхождения любого из элементов value в строку str
  > значение value будет приведено к массиву
  > если вхождение будет не найдено, вернётся значение -1 <br>
  > если задано смещение offset, вхождение будет искаться в подстроке с началом в нём


* func *str_contains(str: string; value: variant; offset: integer = 1): boolean* <br>
  возвращает истину, если в строке str встречается значение любого из элементов value
  > значение value будет приведено к массиву
  > если задано смещение offset, вхождение будет искаться от него


* func *str_starts_with(str: string; value: variant): boolean* <br>
  возвращает истину, если строка str начинается со значения любого из элементов value
  > значение value будет приведено к массиву


* func *str_ends_with(str: string; value: variant): boolean* <br>
  возвращает истину, если строка str заканчивается на значение любого из элементов value
  > значение value будет приведено к массиву


* func *str_find(str: string; value: variant): str_method_find* <br>
  возвращает объект класса-обёртки для поиска подстрок
  > значение values будет приведено к массиву


* func *str_repeat(str: string; count: integer): string* <br>
  возвращает строку str, повторённую count раз


* func *str_pad(str: string; direction: str_pad_direction; value: string; length: integer): string* <br>
  возвращает строку str, дополненную последовательностью value по краям до длины length
  > направление зависит от аргумента direction


* func *str_trim(str: string; direction: str_trim_direction; value: variant): string* <br>
  возвращает строку str, очищенную от последовательностей value по краям
  > значение value приводится к массиву
  > направление зависит от аргумента direction


* func *str_insert(str, value: string; offset: integer; length: variant = nil): string* <br>
  возвращает строку str с заменой подстроки с началом в offset и длиной length на значение value
  > если смещение offset отрицательное, начало подстроки будет считаться с конца строки <br>
  > если длина length:
  > * равна nil, конец подстроки будет соответствовать концу строки
  > * отрицательная, конец подстроки будет считаться с конца строки


* func *str_splice(var str: string; value: string; offset: integer; length: variant = nil): string* <br>
  заменяет подстроку с началом в offset и длиной length на значение value и возвращает удалённую подстроку
  > если смещение offset отрицательное, начало подстроки будет считаться с конца строки <br>
  > если длина length:
  > * равна nil, конец подстроки будет соответствовать концу строки
  > * отрицательная, конец подстроки будет считаться с конца строки


* func *str_replace(str: string; value: variant; replacement: string): string* <br>
  возвращает строку str с заменой значений элементов value на значение replacement
  > значение value будет приведено к массиву


* func *str_format(str: string; value: variant): string* <br>
  возвращает строку str с применением форматирования
  > значение value будет приведено к массиву <br>
  > в результате форматирования последовательности "{}" будут заменены на соответствующие значения из массива значений values <br>
  > чтобы использовать в строке последовательность "{}", её нужно удвоить до "{{}}" <br>
  > чтобы использовать в строке последовательность "{замена}", её нужно обернуть до "{{{}}}"


* func *str_explode(str: string; separator: variant): string[]* <br>
  возвращает массив значений, полученных при разбиении строки str по значениям элементов separator
  > значение separator приводится к массиву
