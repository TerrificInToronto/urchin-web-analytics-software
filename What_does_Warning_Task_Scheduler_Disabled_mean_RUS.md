## Please edit system and help pages ONLY in the moinmaster wiki! For more
## information, please see MoinMaster:MoinPagesEditorGroup.
##acl MoinPagesEditorGroup:read,write,delete,revert All:read
##master-page:HelpTemplate
##master-date:Unknown-Date
#format wiki
#language en


'''О чем предупреждает сообщение "Внимание! Планировщик задач отключен"?'''


Планировщик задач Urchin – это служба, отвечающая за выполнение процессов Urchin. Если ее отключить, Urchin не сможет обрабатывать рабочие операции. Обычно сообщение об ошибке "Внимание! Планировщик задач отключен" появляется в следующих случаях:

  * Служба urchind не запущена. Возможно, произошла перезагрузка сервера, а в скрипте загрузки системы не был указан запуск Urchin.
  * (Только для Unix.) Служба urchind работает, но ее владельцем является не тот пользователь, который владеет дистрибутивом Urchin.

Чтобы определить, работает ли планировщик, выполните следующие действия:
  * Откройте командную оболочку и перейдите в каталог /path/to/urchin/bin/ (используя команду CD).
  * Введите urchinctl status (в ОС Unix введите ./urchinctl status).

Чтобы запустить службу планировщика с помощью командной строки, выполните следующие действия:
  * Откройте командную оболочку и перейдите в каталог /path/to/urchin/bin/ (используя команду CD).
  * Введите urchinctl -s start (в ОС Unix введите ./urchinctl -s start).
  * Если обе службы еще не запущены, введите urchinctl start.

Если служба запущена, владелец процесса Urchin указывается в списке активных процессов на сервере следующим образом: ps -ef | grep urchind.

Вместо строки "User-Name" в результатах будет указан владелец процесса:
```
User-Name 33597 0.0 0.2 352 204 ?? Ss 27Feb08 17:42.18 /usr/local/urchin6/bin/urchind
```
Если этот пользователь не является владельцем дистрибутива Urchin, потребуется остановить службу и снова запустить ее от имени соответствующего пользователя. Введите команду "switch user", чтобы в качестве пользователя выбрать текущего владельца процесса urchind, затем остановите urchinctl. Используйте переключатель "-s", как описано выше. Затем вернитесь к предыдущему пользователю Urchin и запустите urchinctl (с помощью переключателя "-s").