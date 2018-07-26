# Functions.Class


## Описание

Класс с методами для работы с классами.


## Структура

#### Методы класса

* func **class_from**(\_value: variant): class <br>
  возвращает класс для класса или объекта \_value, иначе nil


* func **class_find**(\_name: string): class <br>
  возвращает класс по имени \_name


* func **class_exists**(\_name: string): boolean <br>
  возвращает истину, если класс по имени \_name существует


* func **class_name**(\_class: class): string <br>
  возвращает имя класса \_class


* func **class_description**(\_class: class): string <br>
  возвращает описание класса \_class


* func **class_member_info**(\_class: class; \_name: string): MemberInfo <br>
  возвращает объект класса MemberInfo для члена класса \_class по имени \_name, если он существует, иначе nil


* func **class_prop_info**(\_class: class; \_name: string): MemberInfo <br>
  возвращает объект класса MemberInfo для свойства класса \_class по имени \_name, если оно существует, иначе nil


* func **class_proc_info**(\_class: class; \_name: string): MemberInfo <br>
  возвращает объект класса MemberInfo для процедуры класса \_class по имени \_name, если она существует, иначе nil


* func **class_func_info**(\_class: class; \_name: string): MemberInfo <br>
  возвращает объект класса MemberInfo для функции класса \_class по имени \_name, если она существует, иначе nil


* func **class_method_info**(\_class: class; \_name: string): MemberInfo <br>
  возвращает объект класса MemberInfo для метода класса \_class по имени \_name, если он существует, иначе nil


* func **class_members_info**(\_class: class): MemberInfo[] <br>
  возвращает массив объектов класса MemberInfo для всех членов класса \_class


* func **class_props_info**(\_class: class): MemberInfo[] <br>
  возвращает массив объектов класса MemberInfo для всех свойств класса \_class


* func **class_procs_info**(\_class: class): MemberInfo[] <br>
  возвращает массив объектов класса MemberInfo для всех процедур класса \_class


* func **class_funcs_info**(\_class: class): MemberInfo[] <br>
  возвращает массив объектов класса MemberInfo для всех функций класса \_class


* func **class_methods_info**(\_class: class): MemberInfo[] <br>
  возвращает массив объектов класса MemberInfo для всех методов класса \_class


* func **class_member_info_is_internal**(\_member: MemberInfo): boolean <br>
  возвращает истину, если объект класса MemberInfo \_member соответствует системному члену класса (унаследованному от системного класса)


* func **class_member_info_is_inclass**(\_member: MemberInfo): boolean <br>
  возвращает истину, если объект класса MemberInfo \_member соответствует статическому члену класса (объявленному в блоке inclass)


* func **class_member_info_is_prop**(\_member: MemberInfo): boolean <br>
  возвращает истину, если объект класса MemberInfo \_member соответствует свойству класса


* func **class_member_info_is_proc**(\_member: MemberInfo): boolean <br>
  возвращает истину, если объект класса MemberInfo \_member соответствует процедуре класса


* func **class_member_info_is_func**(\_member: MemberInfo): boolean <br>
  возвращает истину, если объект класса MemberInfo \_member соответствует функции класса


* func **class_member_info_is_method**(\_member: MemberInfo): boolean <br>
  возвращает истину, если объект класса MemberInfo \_member соответствует методу класса


* func **class_members**(\_class: class): string[] <br>
  возвращает массив имён членов класса \_class


* func **class_props**(\_class: class): string[] <br>
  возвращает массив имён свойств класса \_class


* func **class_procs**(\_class: class): string[] <br>
  возвращает массив имён процедур класса \_class


* func **class_funcs**(\_class: class): string[] <br>
  возвращает массив имён функций класса \_class


* func **class_methods**(\_class: class): string[] <br>
  возвращает массив имён методов класса \_class


* func **class_has_member**(\_class: class; \_name: string): boolean <br>
  возвращает истину, если в классе \_class объявлен член с именем \_name


* func **class_has_static_member**(\_class: class; \_name: string): boolean <br>
  возвращает истину, если в классе \_class объявлен статический член (не являющийся объявленным в блоке inclass) с именем \_name


* func **class_has_own_member**(\_class: class; \_name: string): boolean <br>
  возвращает истину, если в классе \_class объявлен пользовательский член (не являющийся унаследованным от системного класса) с именем \_name


* func **class_has_prop**(\_class: class; \_name: string): boolean <br>
  возвращает истину, если в классе \_class объявлено свойство с именем \_name


* func **class_has_proc**(\_class: class; \_name: string): boolean <br>
  возвращает истину, если в классе \_class объявлена процедура с именем \_name


* func **class_has_func**(\_class: class; \_name: string): boolean <br>
  возвращает истину, если в классе \_class объявлена функция с именем \_name


* func **class_has_method**(\_class: class; \_name: string): boolean <br>
  возвращает истину, если в классе \_class объявлен метод с именем \_name


* func **class_get_prop**(\_class: class; \_name: string; \_default_value: variant): variant <br>
  возвращает значение статического свойства класса \_class с именем \_name, если оно объявлено, иначе значение \_default_value

* proc **class_set_prop**(\_class: class; \_name: string; \_value: variant) <br>
  устанавливает значение статического свойства класса \_class с именем \_name, если оно объявлено и доступно для записи


* func **class_call_proc**(\_class: class; \_name: string; \_arguments: variant[] = []): variant <br>
  возвращает результат вызова статической процедуры класса \_class с именем \_name с аргументами \_arguments, если она объявлена, иначе nil


* func **class_call_func**(\_class: class; \_name: string; \_arguments: variant[] = []): variant <br>
  возвращает результат вызова статической функции класса \_class с именем \_name с аргументами \_arguments, если она объявлена, иначе nil


* func **class_call_method**(\_class: class; \_name: string; \_arguments: variant[] = []): variant  <br>
  возвращает результат вызова статического метода класса \_class с именем \_name с аргументами \_arguments, если он объявлен, иначе nil
