## Laboratory work I

<a href="https://yandex.ru/efir/?stream_id=vsVJzkz4i9-s"><img src="https://raw.githubusercontent.com/tp-labs/lab01/master/preview.png" width="640"/></a>

Данная лабораторная работа посвещена изучению утилит для разработки проектов

## Tasks

- [x] 1. Ознакомиться со ссылками учебного материала
- [x] 2. Выполнить инструкцию учебного материала
- [x] 3. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```bash
$ export GITHUB_USERNAME=nastya-asya
$ export GIST_TOKEN=****************************************
$ alias edit=subl
```

```sh
$ mkdir -p ${GITHUB_USERNAME}/workspace
$ cd ${GITHUB_USERNAME}/workspace
$ pwd
/home/nastya-asya/nastya-asya/workspace
$ cd ..
$ pwd
/home/nastya-asya
```

```sh
$ mkdir -p workspace/tasks/
$ mkdir -p workspace/projects/
$ mkdir -p workspace/reports/
$ cd workspace
```

```sh
# Debian
$ wget https://nodejs.org/dist/v6.11.5/node-v6.11.5-linux-x64.tar.xz
$ tar -xf node-v6.11.5-linux-x64.tar.xz
$ rm -rf node-v6.11.5-linux-x64.tar.xz
$ mv node-v6.11.5-linux-x64 node
```

```sh
$ ls node/bin
node  npm
$ echo ${PATH}
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
$ export PATH=${PATH}:`pwd`/node/bin
$ echo ${PATH}
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/home/nastya-asya/workspace/node/bin
$ mkdir scripts
$ cat > scripts/activate<<EOF
export PATH=\${PATH}:`pwd`/node/bin
EOF
$ source scripts/activate
```

```sh
$ gem install gist
```

```sh
$ (umask 0077 && echo ${GIST_TOKEN} > ~/.gist)
```

## Report

```sh
$ export LAB_NUMBER=01
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER} tasks/lab${LAB_NUMBER}
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
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

## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.

```sh
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz

boost_1_69_0.tar.gz 100%[===================>] 106,53M  10,5MB/s    за 11s     

2020-06-03 15:22:13 (9,68 MB/s) - «boost_1_69_0.tar.gz» сохранён [111710205/111710205]
```

2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`

```sh
$ tar -xf boost_1_69_0.tar.gz
```

3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.

```sh
$ ls boost_1_69_0 -f | wc -l
20
```

4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.

```sh
$ find boost_1_69_0/ -type f | wc -l
61191
```

5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).

```sh
$ find boost_1_69_0/ -type f -name '*.h' | wc -l
296                                                    #Количество заголовочных файлов

$ find boost_1_69_0/ -type f -name '*.cpp' | wc -l
13774                                                  #Количество файлов с расширением .cpp

$ find boost_1_69_0/ -type f -not -name '*.cpp' -a -not -name '*.h' | wc -l
47121                                                  #Остальные файлы(не заголовочные и не .cpp)
```

6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.

```sh
$ find boost_1_69_0/ -name 'any.hpp'
boost_1_69_0/boost/proto/detail/any.hpp
boost_1_69_0/boost/fusion/include/any.hpp
boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
boost_1_69_0/boost/fusion/algorithm/query/any.hpp
boost_1_69_0/boost/hana/fwd/any.hpp
boost_1_69_0/boost/hana/any.hpp
boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
boost_1_69_0/boost/any.hpp
boost_1_69_0/boost/type_erasure/any.hpp
boost_1_69_0/boost/xpressive/detail/utility/any.hpp
```

7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.

```sh
$ grep -l -r "boost::asio" boost_1_69_0/
boost_1_69_0/libs/log/src/syslog_backend.cpp
...
boost_1_69_0/libs/log/src/syslog_backend.cpp
```

8. Скомпилирутйе *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).

```sh
$ cd boost_1_69_0
$ ./bootstrap.sh
Building Boost.Build engine with toolset gcc... tools/build/src/engine/bin.linuxx86_64/b2
Unicode/ICU support for Boost.Regex?... not found.
Generating Boost.Build configuration in project-config.jam...

Bootstrapping is done. To build, run:

    ./b2
    
To adjust configuration, edit 'project-config.jam'.
Further information:

   - Command line help:
     ./b2 --help
     
   - Getting started guide: 
     http://www.boost.org/more/getting_started/unix-variants.html
     
   - Boost.Build documentation:
     http://www.boost.org/build/doc/html/index.html
```

9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.

```sh
$ mv boost_1_69_0/=boost_output/lib/ boost-libs/
```

10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.

```sh
$ find . type -f -exec du -h {} +
100K ./libboost_stacktrace_basic.a
...
24K	./boostcpp.jam
```

11. Найдите *топ10* самых "тяжёлых".

```sh
$ find . type -f -exec du -h {} + | sort -rn | head
./libboost_log-vc141-mt-gd-x32-1_70.lib
./libboost_log-vc141-mt-gd-x64-1_70.lib
./libboost_log_setup-vc141-mt-gd-x32-1_70.lib
./libboost_log_setup-vc141-mt-gd-x64-1_70.lib
./libboost_regex-vc141-mt-gd-x64-1_70.lib
./libboost_test_exec_monitor-vc141-mt-gd-x32-1_70.lib
./libboost_test_exec_monitor-vc141-mt-gd-x64-1_70.lib
./libboost_unit_test_framework-vc141-mt-gd-x64-1_70.lib
./libboost_wave-vc141-mt-gd-x32-1_70.lib
./libboost_wave-vc141-mt-gd-x64-1_70.lib
```

```
Copyright (c) 2015-2020 The ISC Authors
```
