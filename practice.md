# Практические занятия

Все примеры кода находятся в **[этом репозитории →](https://github.com/danilzlu/FAM-prog-code-2026-2027.git)**



---

## Практика 5

**[Примеры кода →](https://github.com/danilzlu/FAM-prog-code-2026-2027/tree/main/class-05)**

**[Открыть контест →](https://new.contest.yandex.ru/contests/100180/start)**

> **Важно.** Решения необходимо отправлять только из аккаунта, зарегистрированного с использованием почты в домене `@edu.hse.ru`.

<details>
<summary><strong>Как читать ошибки AddressSanitizer и запускать его локально</strong></summary>

В контесте решения запускаются с **AddressSanitizer (ASan)** — инструментом, который помогает находить ошибки при работе с памятью.

Если программа завершилась с ошибкой ASan, ищите в сообщении строку вида:

```text
ERROR: AddressSanitizer: ...
```

После неё указывается тип обнаруженной ошибки. Например:
- `stack-buffer-overflow` — выход за границы локального массива;
- `heap-buffer-overflow` — выход за границы динамически выделенной памяти;
- `use-after-free` — обращение к памяти после free;
- `double-free` — повторный вызов free для уже освобождённой памяти.
Ниже ASan печатает стек вызовов. В первую очередь ищите строки, в которых указаны имя вашего файла и номер строки, например:
```
#0 0x... in main /path/to/main.c:17
```

Здесь `main.c:17` означает, что ошибку ASan обнаружил на 17-й строке программы. Начинать поиск причины обычно стоит с этой строки и значений используемых на ней индексов и указателей.
Как запустить программу с ASan локально
Для `GCC` или `Clang` скомпилируйте программу так:
```
gcc -std=c23 -Wall -Wextra -g \
    -fsanitize=address \
    program.c -o program
```

и запустите как обычно:
```
./program
```

Ключ `-g` позволяет ASan показывать номера строк исходного файла, а `-fsanitize=address` включает AddressSanitizer.
Если программа читает тест из файла:
```
./program < input.txt
```

Если ASan нашёл ошибку, исправляйте первую обнаруженную ошибку, затем компилируйте и запускайте программу снова. Одна ошибка работы с памятью может привести к множеству последующих сообщений.
</details>


---

## Практика 4

**[Примеры кода →](https://github.com/danilzlu/FAM-prog-code-2026-2027/tree/main/class-04)**

**[Открыть контест →](https://new.contest.yandex.ru/contests/99952/start)**

---

## Практика 3

**[Примеры кода →](https://github.com/danilzlu/FAM-prog-code-2026-2027/tree/main/class-03)**

**[Открыть контест →](https://new.contest.yandex.ru/contests/99202/start)**

---

## Практика 2

**[Примеры кода →](https://github.com/danilzlu/FAM-prog-code-2026-2027/tree/main/class-02)**

**[Открыть контест →](https://new.contest.yandex.ru/contests/99114/start)**

---

## Практика 1

**[Примеры кода →](https://github.com/danilzlu/FAM-prog-code-2026-2027/tree/main/class-01)**

**[Открыть контест →](https://new.contest.yandex.ru/contests/98678/start)**

---

[← На главную](index.md)
