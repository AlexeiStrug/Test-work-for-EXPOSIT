# Руководство пользователя
Для запуска программы необходимо запустить CMD в корне папки и выполнить соответствующую команду запуска с аргументами. Программа выполняется по условию задания описанного ниже. 
Для запуска предварительно нужно создать csv файл с данными которые разделены ";". 
Сборка программы выполнялось с помощью maven через команду:
```sh
mvn clean compile assembly:single
```

#### Пример запуска:
```sh
для вывода в txt файл: java -jar start.jar -l c:\\1.csv -q one -o d:\\result.txt
для вывода в csv файл: java -jar start.jar -l c:\\1.csv -q one -o d:\\result.csv
```
В папке ["Test files"](https://github.com/AlexeiStrug/Search-column-in-file/tree/master/Test%20files) лежит файл через который тестировалось приложение.

# Тестовое задание Java
Готовое задание должно быть доступно на GitHub. В [Readme.md](https://github.com/AlexeiStrug/Search-column-in-file/blob/master/README.md) файле опишите, как запустить вашу программу.
Программы должны быть написаны на Java 8. Для сборки использовать Maven.
#### Задание 2
Создать консольное приложение для поиска столбцов в csv файле и записи результатов в другой файл.
Входные параметры:
- -i исходный файл(формата csv).
- -q строка поиска(Может быть регулярным выражением)
- -o файл результата(txt или csv).

Программа должна найти столбцы, содержащие значение, удовлетворяющее строке поиска и записать их в файл результата.
Регистр должен учитываться (Cat, CAT, cat это все разные слова).
Входной файл должен быть формата csv. Файл с результатом может быть формата csv или txt. Если пишем в csv — столбцы из первого файла преобразуются в строки. Если в txt — все столбцы объединяются в один большой столбец.
#### Пример:

```sh
java -jar myJar.jar -i input.csv -q one -o result.txt 
```
#### input.csv
|  || |
| ------ | ------ | ------ |
| two | one | cat |
| two | girls | fox |
| result | grep | sometimes |
| fear | cap | one |

##### result.txt

||
|------|
| one | 
| girls |
| grep |
| cap |
| cat |
| fox |
| sometimes |
| one |


#### java -jar myJar.jar -i input.csv -q one -o result.csv
##### result.csv
|||||
|-|-|-|-|
| one | girls | grep | cap |
| cat | fox | sometimes|  on| 



