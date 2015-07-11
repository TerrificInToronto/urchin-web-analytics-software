## Please edit system and help pages ONLY in the moinmaster wiki! For more
## information, please see MoinMaster:MoinPagesEditorGroup.
##acl MoinPagesEditorGroup:read,write,delete,revert All:read
##master-page:HelpTemplate
##master-date:Unknown-Date
#format wiki
#language en
'''Источники цен за клик (Urchin 6.5+)'''


Urchin 6.5 предоставляет данные по новому типу источника: источника цен за клик. Источники цен за клик в чем-то схожи с источниками журналов: они позволяют автоматически извлекать данные кампаний с оплатой за клик из внешних источников. Если установлена связь с существующими профилями, такими как источники журналов и фильтры, источники цен за клик позволяют автоматически включать данные о ценах за клик в отчеты Urchin. Источники цен за клик можно создать для Google Ad``Words (Urchin 6.5+) и Yahoo! Search Marketing (Urchin 6.6+).

Внимание! Из-за ограничений версии Ad```Words для начинающих источники цен за клик не будут работать в аккаунтах Ad```Words этой версии. Для использования источников цен за клик необходимо выполнить обновление до стандартной версии Ad``Words.

'''Важное примечание относительно обновления с версии 6.500 до 6.501.''' При обновлении с версии 6.500 до 6.501 необходимо вручную удалить данные о ценах за клик. Для этого удалите все содержимое следующих каталогов:

```
<path_to_urchin_6500_installation>/data/cpc/...
<path_to_urchin_6500_installation>/data/history/cpc/...
```

'''Менеджер источников цен за клик'''

Менеджер источников цен за клик можно найти в разделе "Конфигурация" > "Профили Urchin" в версии Urchin 6.5 +.

![http://www.google.com/urchin/images/wiki/CPC_Source_Manager_Select.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Manager_Select.jpg)

Менеджер источников цен за клик отображает список источников, настроенных на установленном экземпляре программы Urchin, и содержит элементы управления, позволяющие администратору создавать и изменять источники цен за клик.

'''Создание нового источника цен за клик'''

Чтобы добавить и настроить новый источник цен за клик, нажмите кнопку "Добавить" в правом верхнем углу Менеджера источников цен за клик.

![http://www.google.com/urchin/images/wiki/CPC_Source_Manager_Add.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Manager_Add.jpg)

Будет запущен мастер "Добавить источник цен за клик", который предложит вам пошаговые инструкции по добавлению/настройке источника.

В первом шаге укажите следующие данные:

-          Optional Account – укажите, с каким аккаунтом будет связан добавленный источник цен за клик (только для режима Центра данных).

-          CPC Source Name – название источника цен за клик;

-          CPC Source Type (Тип источника цен за клик):

  * '''Google Ad``Words'''

  * Email**– адрес электронной почты для входа в аккаунт Ad``Words, к которому осуществляется доступ, или в аккаунт Центра клиентов;
  * Password** – пароль аккаунта;
  * Developer Token – уникальный идентификатор авторизованного разработчика Ad``Words API (необязательно). В Urchin уже установлен идентификатор разработчика по умолчанию, поэтому оставьте это поле пустым, если только вы не хотите использовать собственный идентификатор.
  * Application Token – идентификатор приложения, который будет использоваться для доступа к Ad``Words API. Это поле также можно оставить пустым.
  * Client E-mail – необходимо указать при использовании логина Центра клиентов (в аккаунте Центра клиентов логином служит адрес электронной почты); это адрес электронной почты, который используется для входа в клиентский аккаунт.
  * Customer ID – необходимо указать при использовании логина Центра клиентов; это идентификатор клиента для аккаунта Ad```Words, к которому осуществляется доступ (номер, например 123-456-7890, указанный в правом верхнем углу экрана в Google Ad```Words). Можно предоставить этот номер вместо адреса электронной почты клиента.
Чтобы проверить настройки источника цен за клик, нажмите кнопку "'''Проверить источник цен за клик'''".

![http://www.google.com/urchin/images/wiki/CPC_Source_Test.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Test.jpg)

  * '''Yahoo! Search Marketing'''

  * Username**– имя пользователя аккаунта Yahoo! Search Marketing, к которому осуществляется доступ. Это может быть адрес электронной почты либо самого рекламодателя, либо агентства, которое осуществляет доступ к отчету от его лица;
  * Password** – пароль аккаунта Yahoo! Search Marketing;
  * Master Account ID**– идентификатор мастер-аккаунта рекламодателя;
    * Account ID** – идентификатор аккаунта рекламодателя;
    * License Key – лицензионный ключ пользователя, осуществляющего вход, рекламодателя или агентства;
    * On-Behalf-of Username – имя пользователя, используемое представителем рекламодателя. Это поле следует заполнять, только если вместо имени пользователя рекламодателя было предоставлено имя пользователя, используемое агентством (необязательно);
    * On-Behalf-of Password – пароль, используемый организацией, представляющей рекламодателя (необязательно).

Нажмите кнопку ''''Готово'''' для завершения процедуры.

![http://www.google.com/urchin/images/wiki/CPC_Source_Finish.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Finish.jpg)

'''Редактирование источника цен за клик'''

Можно изменить настройки добавленного источника цен за клик, удалить его или запланировать загрузку.

![http://www.google.com/urchin/images/wiki/CPC_Source_Edit_Del_Download.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Edit_Del_Download.jpg)

Чтобы изменить настройки существующего источника цен за клик, нажмите кнопку 'Изменить' рядом с ним.

![http://www.google.com/urchin/images/wiki/CPC_Report_Download_Enabled.jpg](http://www.google.com/urchin/images/wiki/CPC_Report_Download_Enabled.jpg)

Вы можете изменить имя пользователя и пароль для входа в аккаунт Ad``Words или Yahoo! Search Marketing, а также включить или отключить загрузку этого источника в будущем. ''Примечание. Даже если вы отключите последующую загрузку отчета, уже загруженные отчеты по-прежнему будут использоваться в профилях, связанных с этим источником цен за клик.''

На вкладке ''''Профили'''' можно связать источник цен за клик с одним или несколькими профилями. Список доступных для связи профилей ограничен текущим аккаунтом Urchin. Данные о ценах за клик из связанных источников будут появляться в отчетах этих профилей.

![http://www.google.com/urchin/images/wiki/CPC_Source_Profiles.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Profiles.jpg)

'''Планирование загрузки источника цен за клик'''

На вкладке '''Расписание''' на экране '''Изменить источник цен за клик''' можно задать настройки загрузки источника цен за клик:

> -          '''"Расписание" – "Интервал загрузки"'''. Загрузка цен за клик разбита на два отдельных этапа. На первом этапе проверяются учетные данные и на сервер цен за клик отправляется запрос. На втором этапе периодически выполняется проверка доступности отчета, пока он не появится на сервере. Второй этап заканчивается загрузкой отчета. Отчет появляется на сервере не сразу, а лишь спустя какое-то время, которое зависит от количества кампаний в аккаунте, объема получаемых данных, текущего уровня загрузки серверов и некоторых других факторов. Этот интервал определяет, когда Urchin начнет проверять доступность отчета после отправки запроса. Для очень крупных аккаунтов с большим объемом трафика рекомендуется установить более продолжительный интервал.

> -          '''"Загрузка" - "Час"''' . Здесь можно настроить время в течение дня, когда следует загружать обновленный отчет по данному источнику цен за клик. Важно! Поскольку данные о ценах за клик извлекаются не каждый час, а раз в день, '''настоятельно рекомендуем''' вам подождать по крайней мере 2 часа после окончания дня в часовом поясе, установленном в вашем аккаунте Ad```Words или Yahoo! Search Marketing. Так вы сможете быть уверены, что на серверах Ad```Words и Yahoo! Search Marketing появились все данные о ценах за клик. Лучше всего указать, чтобы профили с источниками цен за клик обрабатывались уже после загрузки данных о ценах за клик. Благодаря этому в ваших отчетах будут только самые последние данные.

> -            '''"Данные аккаунта" - "Интервал загрузки" (только для Ad```Words в Urchin 6.6+)'''. С помощью этого параметра устанавливается интервал для загрузки структуры аккаунта Ad```Words. Прежде чем вы сможете просматривать метаданные кампании или ключевых слов, пользоваться Генератором ключевых слов, инструментом копирования кампаний или Диспетчером тегов Ad``Words, должна быть загружена структура аккаунта Ad``Words.

![http://www.google.com/urchin/images/wiki/CPC_Source_Schedule_new.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Schedule_new.jpg)

На вкладке "Обновление источника цен за клик" экрана "Глобальные настройки" можно задать глобальные настройки загрузки источника цен за клик.

![http://www.google.com/urchin/images/wiki/CPC_Source_Global_Settings.jpg](http://www.google.com/urchin/images/wiki/CPC_Source_Global_Settings.jpg)