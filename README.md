## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
# Присваиваем переменной GITHUB_USERNAME наше имя пользователя
$ export GITHUB_USERNAME=Ryabchuk15
# Присваиваем переменной GIST_TOKEN наш токен
$ export GIST_TOKEN=**********************
# Связываем вызов команды edit  с вызовом редактора Vim
$ alias edit=vim
```

### Подготовка рабочей директории
```ShellSession
# Создаем директорию workspace
$ mkdir -p ${GITHUB_USERNAME}/workspace
# Переходим в директорию workspace
$ cd ${GITHUB_USERNAME}/workspace
# Выводим полный путь до нашей директории
$ pwd
/home/pcd12/Ryabchuk15/workspace
# Возвращаемся в верхнюю директорию
$ cd ..
# Выводим полный путь
$ pwd
/home/pcd12/Ryabchuk15
```

```ShellSession
# Создаем дочерние директории в workspace
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
# Переходим в директорию workspace
$ cd workspace
```

### Скачиваем nodej
```ShellSession
# Debian
# Скачиваем архив nodej
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-win-x64.tar.xz
# Распаковываем наш архив
$ tar -xf node-v6.11.5-win-x64.tar.xz
# Удаляем архив
$ rm -rf node-v6.11.5-linux-x64.tar.xz
# Переименовываем наш каталог с nodej
$ mv node-v6.11.5-linux-x64 node
```

### Подготовка npm
```ShellSession
# Смотрим содержимое директории node/bin
$ ls node/bin
node npm
# Выводим список директорий, где терминал ищет исполняемые файлы
$ echo ${PATH}
/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/usr/lib/jvm/java-8-oracle/bin:/usr/lib/jvm/java-8-oracle/db/bin:/usr/lib/jvm/java-8-oracle/jre/bin
# Добавляем к переменной PATH путь до бинарных файлов nodej
$ export PATH=${PATH}:`pwd`/node/bin
# Проверяем, добавилась ли наша директория
$ echo ${PATH}
/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/usr/lib/jvm/java-8-oracle/bin:/usr/lib/jvm/java-8-oracle/db/bin:/usr/lib/jvm/java-8-oracle/jre/bin:/home/pcd12/node/bin
# Создаем директорию script
$ mkdir scripts
# Создаем в этой директории файл activate
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
# При помощи команды source содержимое файла будет исполнено как набор команд
$ source scripts/activate
```

### Установка gistup
```ShellSession
# Устанавливаем gistup при помощи npm
$ npm install -g gistup
 /home/pcd12/Ryabchuk15/workspace/node/bin/gistup-open -> /home/pcd12/Ryabchuk15/workspace/node/lib/node_modules/gistup/bin/gistup-open
/home/pcd12/Ryabchuk15/workspace/node/bin/gistup -> /home/pcd12/Ryabchuk15/workspace/node/lib/node_modules/gistup/bin/gistup
/home/pcd12/Ryabchuk15/workspace/node/bin/gistup-rename -> /home/pcd12/Ryabchuk15/workspace/node/lib/node_modules/gistup/bin/gistup-rename
/home/pcd12/Ryabchuk15/workspace/node/lib
└─┬ gistup@0.1.3 
# Смотрим содержимое директории node/bin
$ ls node/bin
gistup  gistup-open  gistup-rename  node  np
```

```ShellSession
# Создаем файл .gistup.json, где будет находится наш gist token
$ cat > ~/.gistup.json <<EOF
{
  "token": "${GIST_TOKEN}"
}
EOF
```

## Report

```ShellSession
# Присваиваем переменной LAB_NUMBER значение 01
$ export LAB_NUMBER=01
# Клонируем репозиторий с л/р в директорию tasks/lab0
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
# Создаем директорию reports/lab01
$ mkdir reports/lab${LAB_NUMBER}
# Копируем README.md в директорию с отчетами и переименовываем его
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
# Переходим в директорию с REPORT.md
$ cd reports/lab${LAB_NUMBER}
# Редактируем его
$ edit REPORT.md
# Создаем gist 'lab01'
$ gistup -m "lab${LAB_NUMBER}" # enter: yes↵
```

## Links

### Unix commands

- [ar](https://en.wikipedia.org/wiki/Ar_(Unix))
- [cat](https://en.wikipedia.org/wiki/Cat_(Unix))
- [cd](https://en.wikipedia.org/wiki/Cd_(command))
- [cp](https://en.wikipedia.org/wiki/Cp_(Unix))
- [cut](https://en.wikipedia.org/wiki/Cut_(Unix))
- [echo](https://en.wikipedia.org/wiki/Echo_(command))
- [env](https://en.wikipedia.org/wiki/Env_(shell))
- [ex](https://en.wikipedia.org/wiki/Ex_(editor))
- [file](https://en.wikipedia.org/wiki/File_(command))
- [find](https://en.wikipedia.org/wiki/Find)
- [ls](https://en.wikipedia.org/wiki/Ls)
- [man](https://en.wikipedia.org/wiki/Man_page)
- [mkdir](https://en.wikipedia.org/wiki/Mkdir)
- [mv](https://en.wikipedia.org/wiki/Mv)
- [nm](https://en.wikipedia.org/wiki/Nm_(Unix))
- [ps](https://en.wikipedia.org/wiki/Ps_(Unix))
- [pwd](https://en.wikipedia.org/wiki/Pwd)
- [rm](https://en.wikipedia.org/wiki/Rm_(Unix))
- [sed](https://en.wikipedia.org/wiki/Sed)
- [touch](https://en.wikipedia.org/wiki/Touch_(Unix))

### Package Managers

- [apt](http://help.ubuntu.ru/wiki/apt) | [dnf](https://en.wikipedia.org/wiki/DNF_(software)) | [yum](https://fedoraproject.org/wiki/Yum/ru)
- [brew](https://brew.sh) | [linuxbrew](http://linuxbrew.sh)
- [npm](https://docs.npmjs.com)

### Software

- [curl](https://www.gitbook.com/book/bagder/everything-curl/details)
- [wget](https://www.gnu.org/software/wget/manual/wget.pdf)
- [clang](https://clang.llvm.org)
- [g++](https://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/G_002b_002b-and-GCC.html)
- [make](https://en.wikipedia.org/wiki/Make_(software))
- [open](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/open.1.html)
- [openssl](https://www.openssl.org)
- [nano](https://www.nano-editor.org)
- [tree](https://linux.die.net/man/1/tree)
- [vim](http://www.vim.org)

```
Copyright (c) 2015-2019 The ISC Authors
```
