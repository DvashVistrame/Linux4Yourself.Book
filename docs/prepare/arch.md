# Целевые архитектуры

Основной целевой архитектурой является `x86_64` (64-разрядная). 

С другой стороны, инструкции в этом руководстве также работают, с некоторыми модификациями, с Power PC, ARM и AMD / Intel x86 (32-bit) процессорами. 

Чтобы собрать систему, которая должна работать на одном из вышеуказанных процессоров, главным условием является существующая операционная система Linux, например уже ранее собранная система по инструкциям этого руководства, Ubuntu, Red Hat/Fedora, SuSE, или другой дистрибутив, который нацелен на требуемую архитектуру.

Также обратите внимание, что 32-разрядный дистрибутив может быть установлен и использоваться как хост-система на 64-разрядном AMD / Intel компьютере.

## О поддержке multilib

В этом руководстве присутствует частичная поддержка multilib.

### Что такое multilib

Процессоры ``X86_64`` могут выполнять как скомпилированный для них код, так и скомпилированный для архитектуры ``i386``.
Но, 32-битные исполняемые файлы работают только с 32-битными библиотеками (а 64-битные - только с 64-битными библиотеками), поэтому для запуска 32-битного исполняемого файла требуются 32-битные версии библиотек которые он использует.
Если в ОС присутствуют библиотеки для нескольких архитектур - её называют multilib системой.

### Зачем это нужно

Некоторые программы с закрытым исходным кодом до сих пор имеют только 32-битные версии. Для Linux таких программ не много, а вот для Windows их существует огромное количество. А для того что бы запустить их необходим Wine с поддержкой multilib.
### Как это реализовано в руководстве

В руководстве присутствуют инструкции в конце многих страниц для multilib систем. Поддержка multilib является опциональной. Если Вам она не нужна - не выполняйте эти инструкции.
Поддержка multilib является частичной - инструкции для сборки 32-битных версий библиотек предоставляются только тогда, когда они необходимы для сборки пакета.

[Подробнее про архитектуры процессора](additional/cpu-arch)
