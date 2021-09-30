# Домашнее задание к занятию «Исключительные ситуации и их обработка. Тестирование исключений»
## Задача №1 - NotFoundException
### Легенда
Вы развиваете приложение с менеджером товаров и решили сделать так, чтобы при попытке удаления несуществующего объекта генерировалось ваше исключение, а не `ArrayIndexOfBoundsException`.

Обратите внимание: это правильный подход, поскольку таким образом вы сообщаете (через генерацию исключения), что это исключение, вписывающееся в вашу логику, а не ошибка программиста.

Что нужно сделать:
1. Взять проект с менеджером, репозиторием и товарами (`Product`, `Book`, `TShirt`), который писали ранее
1. Создайть класс исключения `NotFoundException` отнаследовавшись от `RuntimeException` и реализовать как минимум конструктор с параметром-сообщением 
1. В методе удаления `removeById` сначала проверять, есть ли элемент (для этого прямо из метода `removeById` вызывать метод `findById`: если результат - `null`, тогда выкидывать исключение `NotFoundException`*)
1. Написать 2 автотеста на репозиторий: первый должен проверять успешность удаления существующего элемента, второй - генерации `NotFoundException` при попытке удаления несуществующего элемента
1. Убедиться, что автотесты проходят 

**Итого**: должен быть репозиторий на GitHub, в котором расположен ваш Java-код и автотесты к нему.

Примечание*: обратите внимание, когда генерируются стандартные исключения, всегда передаётся сообщение (на английском языке). Мы рекомендуем делать так же и указывать в сообщении: при удалении по какому конкретно id было сгенерировано ваше исключение.
