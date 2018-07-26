# UnitTesting

## Описание

Набор классов для модульного тестирования. Подробнее о концепции модульного тестирования можно прочитать [здесь](/Docs/UnitTesting/conception.md).


## Структура

* UnitTesting.Assert
* UnitTesting.Case
* UnitTesting.Suite
* UnitTesting.Runner
* UnitTesting.AssertResult
* UnitTesting.CaseResult
* UnitTesting.SuiteResult
* UnitTesting.RunResult


## Использование

Для проведения тестирования необходимо объявить класс - тестовый набор и передать его классу - исполнителю тестовых наборов.

Пример класса - тестового набора:

```

  class inherited UnitTesting.Suite "<опциональный комментарий к набору>";

  inclass


    proc some_case(_case: UnitTesting.Case);

      with _case do

        comment("<опциональный комментарий к ситуации>");

        assert_equal(10 +10, 20);
        assert_equal(20 +20, 40);
        assert_equal(30 +30, 60, "<опциональный комментарий к проверке>");
      end;
    end;
  end
```

Пример передачи класса - тестового набора в класс - исполнитель тестовых наборов и вывод резульатов в консоль:

```

  SmartConsole.new.clear.log_multi(UnitTesting.Runner.run([<массив классов - тестовых наборов>]).to_text);
```

Результат выполнения:

![](/Docs/Images/unit_testing_output.png)

Больше примеров тестовых наборов можно найти в [тестах проекта](/ServerClasses/Tests/).
