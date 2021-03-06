---
title: ConEmu | FAQ - Часть 6

description: Частые вопросы пользователей о работе с ConEmu

breadcrumbs:
 - url: TableOfContents.html#conemu
   title: ConEmu

otherlang:
   en: /en/FAQ-6.html
   ru: /ru/FAQ-6.html
---

# Настройка  {#q-6-settings}

{% include faq_disclaimer_ru.md %}

* [Q. Можно ли запустить ConEmu так, чтобы в нем сразу было открыто несколько вкладок: Far, CMD, PowerShell ?](#q-6-1)
* [Q. Двоятся окна Far Manager.](#q-6-2)
* [Q. Как настроить растровый шрифт?](#q-6-3)
* [Q. Почему горизонтальные рамки отображаются пунктиром/прерывисто?](#q-6-4)
* [Q. Как запустить несколько консолей в сетке 2x2](#q-6-5)
* [Q. Как настроить запуск cmd.exe под Администратором из контекстного меню Проводника Windows](#q-6-6)
* [Q. Как поименовать запускаемые табы при запуске из задачи {Task}](#q-6-7)
* [Q. Как настроить Git Bash Here в ConEmu](#q-6-8)
* [Q. Как экспортировать настройки ConEmu](#q-6-9)
* [Q. Как прицепить открытое консольное окно в новый экземпляр ConEmu](#q-6-10)
* [Q. Как удалить пункты из списка «Create new console»](#q-6-11)



#### Q. Можно ли запустить ConEmu так, чтобы в нем сразу было открыто несколько вкладок: Far, CMD, PowerShell?   {#q-6-1}


A. Можно. Для этого используйте командный файл запуска. Например **startup.txt**:

~~~
>E:\Source\FARUnicode\trunk\unicode_far\Debug.32.vc\far.exe
*/BufferHeight 400 cmd
/BufferHeight 1000 powershell
~~~

и запускайте ConEmu так:

~~~
conemu.exe /cmd @startfile.txt
~~~

В файле каждая строка соответсвует запускаемой команде. Допустимо указание в строке параметра /BufferHeight для установки высоты консольного буфера. Если в начале строки стоит "`>`" - эта консоль будет активной после завершения запуска. Если в начале строки стоит "`*`" - эта консоль будет запущена под администратором.




#### Q. Двоятся окна Far Manager.   {#q-6-2}


A. Это просто консольное окно не спряталось. Проверьте флажок 'Visible' на вкладке 'Features' окна 'Settings' или значение в реестре:

~~~
[HKEY_CURRENT_USER\Software\ConEmu\.Vanilla]
"ConVisible"=hex:00
~~~



#### Q. Как настроить растровый шрифт?   {#q-6-3}

A. Это шрифт Terminal. Например консольный '8 x 12' это 'Terminal 12 x 8' в ConEmu, '12 x 16' -> 'Terminal 16 x 12', и т.п.

> Внимание: В поле 'Charset' необходимо выбрать 'OEM'.
> Лично мне нравится 'Fixedsys 16 x 8', которого в обычной консоли нет.


A. В списке шрифтов можно сразу выбрать, например, `[Raster Fonts 8x12]`.




#### Q. Почему горизонтальные рамки отображаются пунктиром/прерывисто?   {#q-6-4}


A. В некоторых шрифтах ширина соответствующих символов псевдографики оказывается меньше заявленной средней ширины символов шрифта, а именно на него ориентируется ConEmu при автоматическом выборе размеров шрифта рамок. Чтобы избавиться от пунктира, включите флажок «Fix Far borders» и увеличьте ширину шрифта для рамок. Поля имени и ширины шрифта дл рамок расположены под флажком «Fix Far borders» на вкладке 'Main' окна 'Settings'.




#### Q. Как запустить несколько консолей в сетке 2x2   {#q-6-5}


A. Вопрос с [superuser.com](http://superuser.com/q/473807/139371). ConEmu (рекомендуется build 120909 или выше) может отображать несколько консолей одновременно ([SplitScreen](SplitScreen.html)). Вы можете создать задачу (Task) запускающую несколько консолей, например, в сетке 2x2.

~~~
>cmd -cur_console:n
cmd -cur_console:s1TVn
cmd -cur_console:s1THn
cmd -cur_console:s2THn
~~~



#### Q. Как настроить запуск cmd.exe под Администратором из контекстного меню Проводника Windows   {#q-6-6}


A. Читайте ответ на [superuser.com](http://superuser.com/q/470408/139371).




#### Q. Как поименовать запускаемые табы при запуске из задачи {Task}   {#q-6-7}


A. Читайте ответ на [superuser.com](http://superuser.com/q/459154/139371).




#### Q. Как настроить Git Bash Here в ConEmu   {#q-6-8}


A. Читайте ответ на [superuser.com](http://superuser.com/q/454380/139371).




#### Q. Как экспортировать настройки ConEmu   {#q-6-9}


A. Читайте ответ на [superuser.com](http://superuser.com/q/450144/139371).




#### Q. Как прицепить открытое консольное окно в новый экземпляр ConEmu   {#q-6-10}


A. Читайте ответ на [superuser.com](http://superuser.com/q/445394/139371).




#### Q. Как удалить пункты из списка «Create new console»   {#q-6-11}


A. Читайте ответ на [superuser.com](http://superuser.com/a/436273/139371).
