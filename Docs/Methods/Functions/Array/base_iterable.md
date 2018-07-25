# Methods.Functions.Array.BaseIterable


## Описание

Служит родителем для методов array_each, array_filter, array_map, array_reduce (классов [Methods.Functions.Array.Each](/Docs/Methods/Functions/Array/each.md), [Methods.Functions.Array.Filter](/Docs/Methods/Functions/Array/filter.md), [Methods.Functions.Array.Map](/Docs/Methods/Functions/Array/map.md), [Methods.Functions.Array.Reduce](/Docs/Methods/Functions/Array/reduce.md)).


## Указатель

Под указателем ниже подразумевается свойство объекта \__index. Под смещением указателя подразумевается взаимосвязанное изменение свойств \__index и \__item.


## Структура

#### Свойства объекта


  * var **__super**: variant <br>
    хранит ссылку на превосходящий объект или любое другое значение


  * var **__index**: integer <br>
    хранит текущий индекс


  * var **__item**:  variant <br>
    хранит значение по текущему индексу


  * var **__array**: variant[]
    хранит массив, по которому происходит перебор


#### Методы объекта


  * func **__self**: Methods.Functions.Array.BaseIterable <br>
    вовзращает ссылку на текущий объект


  * func **__define_super**(\_value: variant): Methods.Functions.Array.BaseIterable <br>
    устанавливает в свойство \__super ссылку на превосходящий объект \_value (или любое другое значение), возвращает ссылку на текущий объект


  * func **__count**: integer <br>
    возвращает количество элементов массива в свойстве \__array


  * func **__to_index**(\_index: integer): boolean <br>
    устанавливает указатель у элемента массива \__array с индексом \_index; возвращает истину


  * func **__to_begin**: boolean <br>
    устанавливает указатель в шаге до первого элемента массива \__array; возвращает истину
    > таким образом, при последующем выполнении \__next указатель сместится к первому элементу массива


  * func **__to_end**: boolean <br>
    устанавливает указатель в шаге после последнего элемента массива \__array; возвращает истину
    > таким образом, при последующем выполнении \__previous указатель сместится к последнему элементу массива


  * func **__is_within**: boolean <br>
    возвращает истину, если указатель указывает на элемент в пределах массива \__array


  * func **__at_begin**: boolean <br>
    возвращает истину, если указатель указывает на первый элемент массива \__array


  * func **__at_end**: boolean <br>
    возвращает истину, если указатель указывает на последний элемент массива \__array


  * func **__next**: boolean <br>
    смещает указатель к следующему элементу массива \__array; возвращает истину, если указатель указывает на элемент в пределах массива


  * func **__previous**: boolean <br>
    смещает указатель к предыдущему элементу массива \__array; возвращает истину, если указатель указывает на элемент в пределах массива
