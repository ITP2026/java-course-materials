# Краткая памятка JUnit

## Простой тест

```java
class CalculatorTest {

    @Test
    void addsTwoNumbers() {
        Calculator calculator = new Calculator();

        int result = calculator.add(2, 3);

        assertEquals(5, result);
    }
}
```

Структура теста: подготовка данных, действие, проверка результата.

## Частые проверки

```java
assertEquals(expected, actual);
assertTrue(condition);
assertFalse(condition);
assertArrayEquals(expected, actual);
assertThrows(IllegalArgumentException.class, () -> object.call());
```

Для `double` задавайте допустимую погрешность:

```java
assertEquals(2.5, actual, 1e-9);
```

## Имена тестов

Имя должно описывать проверяемое поведение:

```java
void returnsFalseForNumberBelowTwo()
void rejectsEmptyArray()
void replacesValueForEqualKey()
```

Не помещайте несколько несвязанных сценариев в один тест. Не переписывайте внутри теста весь алгоритм из основного кода.

