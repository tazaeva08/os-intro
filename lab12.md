 **<p style="text-align: center;"> РОССИЙСКИЙ УНИВЕРСИТЕТ ДРУЖБЫ НАРОДОВ  
 Факультет физико-математических и естественных наук  
Кафедра прикладной информатики и теории вероятностей**  
  
    

**<p style="text-align: center;">ОТЧЕТ  
ПО ЛАБОРАТОРНОЙ РАБОТЕ № 12  
<ins>Программирование в командном
процессоре ОС UNIX. Ветвления и циклы<ins>**  
дисциплина: <ins>Операционные системы</ins></p>    
  
  
<ins>Студент: Тазаева Анастасия Анатольевна  
Группа: НПИбд-02-20</ins>  

МОСКВА 2021г.  



---------------------------------------------------------------------

**<p style="text-align: center;">Цель работы:**  
Изучить основы программирования в оболочке ОС UNIX. Научиться писать более сложные командные файлы с использованием логических управляющих конструкций и циклов.


**<p style="text-align: center;">Ход работы:**  
1. *Используя команды getopts grep, написать командный файл, который анализирует командную строку с ключами:  
– -iinputfile — прочитать данные из указанного файла;  
– -ooutputfile — вывести данные в указанный файл;  
– -pшаблон — указать шаблон для поиска;  
– -C — различать большие и малые буквы;  
– -n — выдавать номера строк.  
а затем ищет в указанном файле нужные строки, определяемые ключом -p*    
  
Для начала создала 3 файла, 1- файл, который будет читаться (i)(abc.sh рис.3), 2- файл, в который будут вводиться данные(efg.sh рис.4), 3- командный файл(рис.1), в нем и написан скрипт(рис.2). Далее выполнила файл(рис.5)
**<p style="text-align: center;"><img src="рис1.png">  
(рис.1)  
<img src="рис2.png">   
(рис.2)  
<img src="рис3.png">   
(рис.3)  
<img src="рис4.png">   
(рис.4)  
<img src="рис5.png">   
(рис.5)**</p>  
2. *Написать на языке Си программу, которая вводит число и определяет, является
ли оно больше нуля, меньше нуля или равно нулю. Затем программа завершается
с помощью функции exit(n), передавая информацию в о коде завершения в
оболочку. Командный файл должен вызывать эту программу и, проанализировав
с помощью команды $?, выдать сообщение о том, какое число было введено.*   

Создали файл с скриптом(рис.6), который определяет, какое число(больше-меньше-равно-0). Выводит числа 0 1 2, 0 - число отрицательное, 1 - число положительное, 2 - это число нуль. Также был создан командный файл, он как раз-таки и читает этот файл с программой, и получая число 0/1/2 он выводит для каждого сообщение.(рис.7). Проверили работу(рис.8)  
**<p style="text-align: center;"><img src="рис6.png">  
(рис.6)  
<img src="рис7.png">  
(рис.7)  
<img src="рис8.png">  
(рис.8)**</p>  
3. *Написать командный файл, создающий указанное число файлов, пронумерованных последовательно от 1 до N (например 1.tmp, 2.tmp, 3.tmp,4.tmp и т.д.).
Число файлов, которые необходимо создать, передаётся в аргументы командной
строки. Этот же командный файл должен уметь удалять все созданные им файлы
(если они существуют).*  

Создали файл со скриптом (рис.9 и 10). Файл выводит на экран какое кол-во необходимо создать файлов, с клавиатуры вводим число. Создаются файлы от 1 до n, сделали так, чтобы программа выводила содержимое директории домашней. Далее по необходимости удаляются файлы, и снова выводится содержимое дом.дир.(рис.11)  
**<p style="text-align: center;"><img src="рис9.png">  
(рис.9)  
<img src="рис10.png">  
(рис.10)  
<img src="рис11.png">  
(рис.11)**</p>  
4. *Написать командный файл, который с помощью команды tar запаковывает в
архив все файлы в указанной директории. Модифицировать его так, чтобы запаковывались только те файлы, которые были изменены менее недели тому назад
(использовать команду find).*  

Написала командный файл, который с помощью команды tar запаковывает
в архив все файлы в указанной директории. Запаковываются только те файлы, которые были изменены менее недели тому назад (использовал команду find). (рис.12) и проверила(рис.13)  
**<p style="text-align: center;"><img src="рис12.png">  
(рис.12)  
<img src="рис13.png">  
(рис.13)**</p>  

-------------------------------------------------------
**<p style="text-align: center;">Контрольные вопросы:**  
1. Каково предназначение команды getopts?  
Команда getopts используется для разбора параметров и проверки опций на допустимость.  
Осуществляет синтаксический анализ командной строки, выделяя флаги, и используется для объявления переменных.  
2. Какое отношение метасимволы имеют к генерации имён файлов?  
Метасимволы отвечают за параметры выдачи файлов, а следовательно могут вносить иной смысл, нежели прямое значение как символа.  
Например:  
- * — соответствует произвольной, в том числе и пустой строке;  
- ? — соответствует любому одному символу;  
- [c1-c1] — соответствует любому символу, лексикографически на ходящемуся между символами c1 и с2.  
- echo * — выведет имена всех файлов текущего каталога, что представляет собой простейший аналог команды ls;  
- ls *.c — выведет все файлы с последними двумя символами, равными .c.  
- echo prog.? — выдаст все файлы, состоящие из пяти или шести символов, первыми пятью символами которых являются prog. .  
- [a-z]* — соответствует произвольному имени файла в текущем каталоге, начинающемуся с любой строчной буквы латинского алфавита.  
3. Какие операторы управления действиями вы знаете?  
for, break , while, until, case ,continue, if, else  
4. Какие операторы используются для прерывания цикла?  
break  
5. Для чего нужны команды false и true?  
Это логические значения (0 и 1 соответственно). Можно использовать как полее понятный вариант
6. Что означает строка if test -f man$s/$i.$s, встреченная в командном файле?  
Условие существование файла man$s/$i.$s  
7. Объясните различия между конструкциями while и until  
while - проверка условия затем выполнение тела цикла  
until - выполнение тела цикла затем проверка условия  
  
  ----------------------------------------------------------------------------------------------------
**ВЫВОД:**  
  
В ходе работы мы изучили основы программирования в оболочке ОС UNIX. Научились писать более сложные командные файлы с использование логических управляющих инструкций и циклов.
