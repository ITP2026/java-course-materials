# Частые ошибки

## `class X is public, should be declared in a file named X.java`

Имя файла должно совпадать с именем публичного класса с учетом регистра.

## `non-static method cannot be referenced from a static context`

Экземплярный метод вызывается через объект. Не добавляйте `static` автоматически: проверьте, должен ли метод работать с состоянием объекта.

## `Cannot resolve symbol`

Проверьте имя, import, package, расположение файла и выбранную JDK.

## `NullPointerException`

Найдите выражение слева от точки или операцию распаковки. Не закрывайте проблему общим `catch`; установите источник недопустимого `null`.

## Тесты не обнаружены

Проверьте каталог `src/test/java`, import `org.junit.jupiter.api.Test`, аннотацию `@Test` и имя Maven-модуля.

## Maven не видит модуль

Запускайте wrapper из корня репозитория и сверяйте имя после `-pl` с корневым `pom.xml`.

## Изменения отсутствуют в PR

Проверьте `git status`, текущую ветку, наличие commit и выполнение `git push`.

## В Git попал `target`

Удалите его из индекса, но сохраните локально:

```bash
git rm -r --cached lab01/target
```

Убедитесь, что `target/` указан в `.gitignore`.
