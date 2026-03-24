# Codacy

https://www.codacy.com/

## Описание программного анализатора

Codacy — это автоматизированная платформа для статического анализа качества и безопасности кода. Она помогает разработчикам выявлять ошибки, уязвимости и стилистические недочёты на этапе разработки.

Основные возможности:

* Статический анализ кода

* Анализ безопасности

* Расчет метрик качества кода

    * Качество кода
    * Технический долг
    * Покрытие тестами
    * Цикломатическая сложность
    * Дублирование кода

## Полученные issues (избранные)

### Проблемы безопасности и надежности

1. CloseResource

`Ensure that resources like this <...> object are closed after use`

Описание: Ресурсы (файлы, сокеты, каналы, ...) не закрыты, что может привести к утечкам памяти и дескрипторов

Встречается 95 раз

Риск: Высокий. Утечки ресурсов могут привести к падению приложения при длительной работе

2. AvoidAccessibilityAlteration

`You should not modify visibility of constructors, methods or fields using setAccessible()`

Описание: Использование `setAccessible(true)` для обхода модификаторов доступа

Встречается 2 раза

Риск: Высокий. Нарушает инкапсуляцию, привести к нестабильности при обновленияи версий JVM

3. ReturnEmptyCollectionRatherThanNull

`Return an empty collection rather than null`

Описание: Методы возвращают null вместо пустой коллекции, что повышает риск NullPointerException у вызывающего кода

Встречается 4 раза

Риск: Средний. Увеличивает вероятность ошибок в клиентском коде

4. PreserveStackTrace

`New exception is thrown in catch block, original stack trace may be lost`

Описание: Потеря корневой причины исключения

Встречается 1 раз

Риск: Средний. Усложняет отладку

5. EmptyCatchBlock

`Avoid empty catch blocks`

Описание: Исключения перехватываются, но игнорируются, что может скрывать критические ошибки

Встречается 3 раза

Риск: Высокий. Подавление исключений может привести к ошибкам в работе системы

### Производительность

1. GuardLogStatement

`Logger calls should be surrounded by log level guards`

Описание: Не проверяется включенность данного уровня логгирования, что может приводить к бесполезным тратам CPU, если уровень выключен

Встречается 115 раз

Риск: средний, если нагрузка высокая, генерируется очень много логов

2. AvoidStringBufferField

`StringBuffers can grow quite a lot, and so may become a source of memory leak (if the owning class has a long life time)`

Описание: StringBuffers не следуюет использовать как поля классов, так как они быстро разрастаются и могут стать причиной утечки памяти

Встречается 4 раза

Ризк: низкий

### Стиль кода

1. UnnecessaryConstructor + UncommentedEmptyConstructor

`Unnecessary use of fully qualified name <...> due to existing same package import <...>`

Описание: Дефолтный (пустой) конструктор и так генерируется компиллятором, можно не писать

Встречается 35 раз

Риск: низкий

2. ForLoopCanBeForeach

`This for loop can be replaced by a foreach loop`

Описание: Можно заменить цикл на современный for each

Встречается 15 раз

Риск: низкий

3. LooseCoupling

`Avoid using implementation types like <...>; use the interface instead`

Описание: Использование конкретных реализациях как типы полей вместо интерфейсов

Встречается 26 раз

Риск: низкий

4. UnnecessaryFullyQualifiedName

`Unnecessary use of fully qualified name <...> due to existing same package import <...>`

Описание: Использование полного имени вместо простого при наличии импорта

Встречается 14 раз

Риск: низкий

### Многопоточность

1. AvoidUsingVolatile

`Use of modifier volatile is not recommended.`

Описание: Использование модификатора volatile не рекомендуется

Встречается 6 раз

Риск: низкий

2. UseNotifyAllInsteadOfNotify

`Call Thread.notifyAll() rather than Thread.notify()`

Описание: Использование `notify()` вместо `notifyAll()` будит только 1 поток, что может быть логической ошибкой, если больше одного потока ждут сигнал

Встречается 2 раза

Риск: средний, но часты ложноположительные срабатывания

3. AssignmentToNonFinalStatic

`Possible unsafe assignment to a non-final static field in a constructor`

Описание: Изменение статической переменной в конструкторе не является потоко-безопасным

Встречается 1 раз

Риск: средний

### Ошибки

1. CompareObjectsWithEquals

`Use equals() to compare object references.`

Описание: Сравнение ==, а не equals может работать некорректно (будут сравниваться ссылки)

Встречается 8 раз

Риск: средний

2. IdenticalCatchBranches

`<...> branch identical to <...> branch`

Описание: одинаковые catch блоки для разных типов исключений

Встречается 5 раз

Риск: низкий

3. AssignmentInOperand

`Avoid assignments in operands`

Описание: Следует избегать присваиваний в условиях

Встречается 4 раза

Риск: низкий

### Архитектура

1. SingleMethodSingleton

`Class contains multiple getInstance methods. Please review.`

Описание: Класс содержит несколько методов, возвращающих экземпляр, что противоречит паттерну Singleton

Встречается 2 раза

Риск: низкий

2. UseUtilityClass

`All methods are static.  Consider using a utility class instead. Alternatively, you could add a private constructor or make the class abstract to silence this warning`

Описание: Класс содержит только статические методы, но не имеет приватного конструктора, что позволяет создавать его экземпляры

Встречается 1 раз

Риск: низкий
