# QE (quadratic equation)

![](docs/example.png)

Программа для решения квадратного уравнения **ах2 + bх + с = 0**

## Содержание
[Структура проекта](#структура-проекта)

[Как использовать приложение](#как-использовать)

[Сборка приложения](#как-собрать-приложение)

[Тестирование](#тестирование)


## Структура проекта
```bash
├── Makefile # makefile для удобного запуска
├── README.md # Краткая документация, сейчас её читаете =)
├── bin # папка с бинарниками
│   ├── qe
│   ├── qe.exe
│   └── qe_linux
├── docs # материалы для документации
│   ├── example.png
│   ├── test-table.png
│   └── tests.png
├── go.mod # файл с зависимостями
├── main.go # точка входа
└── main_test.go # тесты
```

## Как использовать?

Все бинарные файлы лежат в папке `bin/`

```bash
├── bin
│   ├── qe # mac os binary
│   ├── qe.exe # windows binary
│   └── qe_linux # linux binary
```

Запустите один из файлов, ориентируясь на вашу ОС

Вы можете запустить программу используя Golang

`go run main.go`

## Как собрать приложение

Для сборки приложения можно использовать утилиту [make](https://www.gnu.org/software/make/#download)

в таком случае собрать приложение можно с помощью команды `make build`.

Так же можно собрать приложение используя возможности языка golang


`go build -o bin/app main.go`

Пример:

Для Unix:
`go build -o bin/qe main.go`

для Windows:
`go build -o bin/qe.exe main.go`

## Тестирование

Минимальный набор тестов

| № Теста      | a |  b | c | Ожидаемый результат | Что проверяется |
| ----------- | -----------|-----------|-----------|-----------|-----------|
|1| 2 | -5 | 2 | x1=2, x2=0.5 | Случай вещественных корней |
|2| 3 | 2 | 5 | Сообщение | Случай комплексных корней |
|3| 3 | -12 | 0 | x1=4, x2=0 | Нулевой корень |
|4| 0 | 0 | 10 | Сообщение | Неразрешимое уравнение |
|5| 0 | 0 | 0 | Сообщение | Неразрешимое уравнение |
|6| 0 | 5 | 17 | Сообщение | Неквадратное уравнение |
|7| 9 | 0 | 0 | x1=0, x2=0 | Нулевые корни |

Для того, чтобы провести тестирование необходимо выполнить команду `go test -v`

![](docs/tests.png)