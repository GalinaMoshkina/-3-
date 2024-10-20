# Лабораторная работа 2
## Задание лабораторной работы

На основе изученного материала лабораторной работы, лекций (2 и 3), дополнительных источников напишите скрипт, который на вход принимает IPv4-адрес в десятичном формате, а на выходе обеспечивает данный IP-адрес в двоичном формате.

Пример входных данных:

```192.168.10.1```

Пример выходныx данных:

```11000000.10101000.00001010.00000001```  

## Решение  

Начнем с идеи. Нам нужно пробежаться по каждому числу IPv4-адреса, чтобы переделать его в 2-СС. Для этого нужно переделать формат самой строки. Через цикл мы меняем СС, а после цикла добавляем снова разделители в виде "."  

Создаем файл `new.bash` с помощью команды `touch`. Далее, открываем файл для редактирования с помощью команды `gedit` и пишем код:  

![Снимок экрана 2024-10-20 194738](https://github.com/user-attachments/assets/2518e53a-020b-4b4e-af43-96b9f5facd7c)


Построковое объяснение  
1 - прописываем `#!/bin/bash` для работы с bash  
3 - `ip_y=$1` - получаем на вход IPv4-адрес  
4 - `ip=${ip_y//./ }` - заменяем в строке адреса символ `.` на ` `  
5 - создаем массив `rez=()`, в котором будет храниться итоговый результат  
7 - начало цикла. пробегаемся по нашей строке `ip`  
9 - в переменную `transition` мы записываем двоичную запись одного числа  
10 - в переменную `zero` мы дописываем недостающие "незначащие" нули  
11 - добавляем в наш массив `rez` получившееся число  
14 - создаем переменную `out`, которую как раз мы и будем выводить. В ней мы меняем формат строки, а именно добавляем разделитель между числами - `.`  
16 - печатаем наш результат  

## Дополнительные источники

1. [Присваивание значений переменным.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#VARASSIGNMENT)
2. [Подстановка переменных.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#VARSUBN)
3. [Арифметические операции.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#ARITHEXP)
4. [Проверка условий.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#TESTS)
5. stackoverflow.com
6. Хорошая ĸнига по Shell/bash в Linux - "Learn Linux Shell Scripting – Fundamentals of Bash 4.4" Sebastiaan
Tammer
7. [Функции.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#FUNCTIONS)
8. [Функции и рекурсивные функции.](https://habr.com/ru/company/ruvds/blog/327248/)
9. [Циклы.](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#LOOPS)
10. [Массивы](https://se.ifmo.ru/~ad/Documentation/ABS_Guide_ru.html#ARRAYS)
11. [Про двоичную систему и IP-адрес](https://zametkinapolyah.ru/kompyuternye-seti/4-4-dvoichnye-chisla-i-dvoichnaya-sistema-schisleniya-perevod-chisla-v-dvoichnuyu-sistemu-schisleniya-iz-desyatichnoj.html)
12.  В. Олифер, Н. Олифер "Компьютерные сети. Принципы, технологии, протоколы. Учебник" (2016)
