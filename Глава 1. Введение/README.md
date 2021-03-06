# Введение в системы контроля версий

## Зачем?

Позволяют откатывать проект или файл до определенной версии, просмотривать изменения между версиями, узнавать, кто что менял. Повышение стойкости проекта в целом (в плане сохранения файлов).

## Немного истории

1. Локальные СКВ ( версия означает хранение текущего состояния(всех файлов) в определенной для данной версии директории). Решает проблему версий, но не проблему совместного использования
2. Централизованные ( Все файлы находятся на одном сервере и множество разработчиков могут получать к ним доступ). Решает проблему версий и множественного доступа, но не единой точки отказа
3. Децентрализованные ( Файлы хранятся на удаленном сервере, а так же готовая копия проекта на машине у каждого разработчика).

## Почему Git и откуда он взялся 

Git разработка Линуса Торвольдса, как необходимое решение для дальнейшей разработки ядра Linux, так как они прекратили сотрудничество с BitKeeper. 
В результате, наработавшись с BitKeeper и вынеся множество уроков, был создан Git - утилита, которая позволила достичь следующие цели:
* Скорость работы при работе с огромными проектами
* Параллельная разработка
* Децентрализация
* Разумное использование дискового пространства

## Основы

* Git хранит снимки, а не историю изменения файлов. То есть для каждого снимка он запоминает текущее состояние файлов, 
а для неизменненых файлов устанавливает ссылку на предыдущую версию.

* Локальность (практически любая команда выполняется на локальном репозитории и очень быстро). 
Нагрузка на сервер и временные траты только на синхронизацию, по желанию.

* Целостность (для любого объекта в гите используется вычисление хеш-суммы SHA-1, что не позволит сделать изменения без ведома).


## Состояния

Файл может находиться в 3 состояниях :
1. Commited - Файл находится в локальном репозитории в том же виде, что и сейчас.
2. Modified - Версия файла, которая отличается от той, что в репозитории.
3. Staged - Версия файла, которая добавлена для включения в следующий снимок.

## Также

.git директория, которая хранит метаданные всех объектов гита.

working директория, которая является по сути разархивированной версией, для редактирования.

Область подготовленных файлов находится в гит директории и представляется собой файл с информацией для последующего комита.


## Настройки

Настройки в гите бывают системные, глобальные и локальные.

/etc/gitconfig - системные настройки для всех пользователей и репозиторием ключ для редактирование и просмотра --system

~/.gitconfig или ~/.config/git/config - настройки конкретного пользователя  ( ключ --global )

.git/config - настройки для конкретного пользователя и конкретного репозитория.

Настройки перезаписываются каскадно, сверху вниз.