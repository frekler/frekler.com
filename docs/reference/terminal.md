`dd if=/dev/urandom of=temp_5GB_file bs=10 count=500`
// создать файл большого размера

`find . -type f -name best_movies.txt`
// поиск файла best_movies.txt



`pwd` (print working directory)
чтобы узнать где мы находимся

`ls` (list)
без флагов (флаги ставятся после тире)
что находится в папке

`ls -1`
вывод в столбик 

папки выделяются слешем в конце

`ls -l`
long
длинный формат вывода

первый символ d - directory
права доступа для пользваотелей (владелец/которые находятся с владельцем в одной группе/что оставшиеся могут делать)

владелец/группа/размер/время создания

`ls -lh`
(h - human readable - размер выведется в единицах удобочетаемых единицах для чел)

`ls dir1/`
что находится в папке dir1 (которая нах здесь же)

`ls -l dir1/`
тоже можно

`cd`
change directory
`cd dir1` (зайти в dir1)

TAB для автоподстановки

--

`cd ..`
подняться на уровень выше

--

`cd ../..`
подняться на уровень выше и еще на уровень выше

----

`cd BASH/test/`
перейти в 

---

есть способ вернуться туда откуда мы пришли (те в то место где находились до этого)
`cd -`

----

`clear`

---

`mv`
move

`mv [что переносим - аргумент] [куда - аргумент]`
`mv text.txt dir1/`

--

`mv dir1/text.txt ./`
переместить в текущую директорию


`mv text1.txt text1_copy.txt`
переименование файла




command key
clear


cp
copy

`cp text1.txt dir3/`
копирование файла в дир3



`cp -a dir3 dir4/`
копирование папки
флаг -a - сочетание трех других флагов и он позволяет копировать папки
флаг -а можно юзать и для файлов



`touch`
создает файлы

`touch app.js`
`touch a.txt b.txt c.txt`
создаст сразу 3 файла

а можно так
`touch {a,b,c}.txt`
создаст 3 файла a.txt b.txt c.txt

`touch index.{js,html}`
`index.js и index.html`




`mkdir`
make directory

`mkdir dir1`

`mkdir dir1/dir2`

или
`mkdir -p dir1/dir2/dir3`
флаг -p позволяет создавать промежуточные папки которые отсутствуют на момент создания конечноц папки
те позволяет создать всю структуру вложенных папок



`rm`
удаление файла
`rm a.txt`

rm без флагов удалять папки не может
`rm -r dir1`
-r рекурсивно
удалит все внутри 
можно добавить флаг `-i` (интерактивный режим) и он будет запрашивать разрешения на удаления

а флаг `-f`наоборот пропустит(!) все запросы (попытки терминала спросить) на удаление

`rm` удаляет все сразу из системы (без корзины)

поэтому особо аккуратно с `rm -rf`

`rm -rf ./*.txt`
удали все файлы .txt из текущей папки

`rm -rf ./index*`
удалит все файлы начинающиеся на index

т.о. `-rf` можно юзать и для папок и для файлов




`rm -rf ./dir1`







поиск файла
`find [с какого места]`
`find . -type f -name app.js`
`.` - с самой папки где находится
`-type f` - ищем файлы
`-type d` - ищем директорию
`-name` с именем




vim

`vim /dir1/app.js` - открываем

командный режим по умолчанию
включить режим вставки - i
сохранение - esc (командный режим) и `shift:x!` (сохранить)
выйти из файла ничего не сохраняя - `shift:q!` (выйти без сохранения)
перемещение вверх-вниз - j-вниз -kнаверх
h-вправо l-влево
в конец - `shift+$`

удалить ; в конце всех строк
в командном режиме
выделить символ и нажимаем x





`cat app.js` - тоже посмотреть содержимое файла










`man ls`
покажет документацию по ls
q - выйти






razmusorim.ru
размусорим.рф
vseecologi
oureco.ru



zsh command not found  
https://www.easeus.com/computer-instruction/zsh-command-not-found.html  
https://stackoverflow.com/questions/18428374/in-mac-always-getting-zsh-command-not-found  
