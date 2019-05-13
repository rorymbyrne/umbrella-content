---
index: 7
title: Mailvelope
---
Mailvelope  
====================

Безопасная веб-почта

** Урок для чтения: [Защита файлов](umbrella://information/protecting-files), [E-mail](umbrella://communications/email) **
** Уровень: ** Продвинутый
** Требуемое время: ** 30-60 минут
** Обновлено: ** Апрель 2018 (некоторые изображения датируются более ранними версиями)
** Источники: ** Безопасность-в-коробке, [MAILVELOPE - OPENPGP ШИФРОВАНИЕ ДЛЯ WEBMAIL](https://securityinabox.org/en/guide/mailvelope/web/)

** Использование Mailvelope даст вам: **

- Возможность отправлять и получать зашифрованную сквозным методом электронную почту, которая не может быть прочитана третьими лицами.
- Возможность цифровой подписи вашей электронной почты и аутентификации подписанной электронной почты от других.


** Расположение загрузки: ** [https://www.mailvelope.com/en]((https://www.mailvelope.com/en))
** Версия, используемая в этом руководстве: ** 1.5.1
** Лицензия: ** Бесплатное и открытое программное обеспечение
** Системные требования: ** ** Mozilla Firefox, ** ** Google Chrome ** или ** Chromium **, работающие на Linux, Windows или Mac.




# 1. Введение

Mailvelope - это расширение браузера, которое позволяет шифровать, расшифровывать, подписывать и аутентифицировать почтовые сообщения и файлы с использованием OpenPGP. (Расширение браузера - это программный компонент, который добавляет дополнительные функции в ваш веб-браузер.) Он работает с веб-почтой и не требует загрузки или установки дополнительного программного обеспечения. Хотя в Mailvelope отсутствуют многие функции, предоставляемые Thunderbird, Enigmail и GnuPG, для пользователей веб-почты это, вероятно, самый простой способ начать использовать преимущества сквозного шифрования.

## 1.0. Что нужно знать о Mailvelope перед началом работы

Mailvelope опирается на форму * криптографии с открытым ключом *, которая требует от каждого пользователя создавать свою собственную пару * ключей *. Эта * пара ключей * может использоваться для шифрования, дешифрования и подписи цифрового контента, такого как e-mail сообщения. Способ включает * закрытый ключ * и * открытый ключ *:

- Ваш ** закрытый ключ ** чрезвычайно чувствителен. Любой, кому удалось получить копию этого ключа, сможет читать зашифрованный контент, предназначенный только для вас. Они также смогут подписывать сообщения, так как будто они * пришли * от вас. Ваш * закрытый ключ * сам по себе зашифрован с использованием ключевой фразы, которую вы выберете при создании * пары ключей *. Вы должны выбрать надежную фразу-пароль и следить за тем, чтобы никто не получил доступ к вашему * секретному ключу *. Вы будете использовать свой * закрытый ключ * для расшифровки сообщений, отправленных вам теми, у кого есть копия вашего * открытого ключа *.

- Ваш ** открытый ключ ** предназначен для совместного использования с другими и не может использоваться для чтения зашифрованного сообщения или подделки подписанного. Получив открытый ключ корреспондента, вы можете начать отправлять ему зашифрованные сообщения. Только он сможет расшифровать и читать эти сообщения, потому что только у него есть доступ к * секретному ключу *, который соответствует * открытому ключу *, который вы используете для шифрования. Аналогичным образом, для того, чтобы кто-то * отправил вам * зашифрованное письмо *, он должен получить копию вашего * открытого ключа *. Важно убедиться, что * открытый ключ *, который вы используете для шифрования электронной почты, действительно принадлежит тому человеку, с которым вы пытаетесь установить связь. Если вы или ваш корреспондент обмануты с помощью шифрования электронной почты с неверным открытым ключом, ваш разговор не будет безопасным.

Mailvelope также позволяет вам прикреплять ** цифровые подписи ** к вашим сообщениям. Если вы * подписываете * сообщение, используя свой * закрытый ключ *, любой получатель с копией вашего * открытого ключа * может убедиться, что оно было отправлено вами и что его содержимое не было подделано. Точно так же, если у вас есть * открытый ключ корреспондента *, вы можете проверить его цифровые подписи.

Mailvelope позволит вам:

- Создать пару ключей шифрования
- Экспортировать ваш открытый ключ, чтобы вы могли поделиться им с другими
- Импортировать открытые ключи других людей
- Составлять, шифровать и подписывать сообщения электронной почты
- Расшифровывать и аутентифицировать сообщения
- Шифровать, прикреплять и дешифровать файлы

Вашим корреспондентам не обязательно использовать Mailvelope, но они должны использовать некоторые формы шифрования OpenPGP, некоторые из которых перечислены ниже.

Так как Mailvelope является расширением браузера, он будет работать только с браузером, в котором он был установлен. Если вы хотите использовать Mailvelope с другим браузером, вам придется установить его заново. Это правда, даже если оба браузера находятся на одном компьютере. Вам также нужно будет экспортировать все свои ключи и импортировать их в новую копию Mailvelope.


## 1.1 Другие инструменты, сродни Mailvelope

Поскольку Mailvelope является расширением браузера, он работает на большинстве настольных операционных систем. Список включает GNU / Linux, Microsoft Windows и Mac OS X. Он не работает на мобильных устройствах Android или iOS. Ниже приведены несколько бесплатных и открытых альтернатив:

- [** Thunderbird с Enigmail **](../../thunderbird/windows) полный почтовый клиент с добавленным шифрованием PGP для GNU / Linux, Microsoft Windows и Mac OS X
- [** GPG4Win **](https://www.gpg4win.org/) PGP набор инструментов шифрования электронной почты и файлов для Microsoft Windows
- [** GPG Tools Suite **](https://gpgtools.org/) для Mac OS X
- [** gpg4usb **](https://www.gpg4usb.org/) автономный портативный инструмент PGP для GNU / Linux и Microsoft Windows
- [** Mailpile **](https://www.mailpile.is/) Предстоящий почтовый клиент, совместимый с OpenPGP, для GNU / Linux, Microsoft Windows и Mac OS X


# 2. Генерация и обмен ключами шифрования

Прежде чем начать шифрование и расшифровку электронной почты, необходимо выполнить три подготовительных шага:

- Сгенерируйте свою пару ключей шифрования (или импортируйте ее, если она у вас уже есть)
- Экспортируйте ваш открытый ключ и отправьте его своим контактам
- Импортируйте открытые ключи от ваших контактов


## 2.1 Генерация пары ключей

Чтобы сгенерировать пару ключей, откройте браузер, в котором вы установили Mailvelope, и выполните следующие действия.

**Шаг 1**. ** Нажмите **значок **блокировки** Mailvelope на панели инструментов браузера, чтобы активировать следующий экран:

![](mailvelope-all-en-v01-002.png)

**Шаг 2**. ** Нажмите ** ** [Параметры] **, чтобы активировать экран Mailvelope * Параметры *

![](mailvelope-all-en-v01-003.png)

**Шаг 3**. ** Нажмите ** ** [Создать ключ] ** и ** введите ** свою информацию в поля, как показано ниже:

![](mailvelope-all-en-v01-004.png)

**Важно:**

- Выберите надежную фразу-пароль для защиты вашего закрытого ключа. (Узнайте, как создать надежные [Пароли](umbrella://information/passwords/beginner).)
- Вам не нужно использовать свое настоящее имя при создании ключа, но вы должны ввести e-mail адрес учетной записи, с которой вы собираетесь использовать Mailvelope. Если хотите, вы можете создать новую учетную запись электронной почты специально для этой цели.
- Мы рекомендуем вам создать уникальную пару ключей для каждого e-mail аккаунта, который вы хотите использовать с Mailvelope.

** Шаг 4 **. ** Снимите отметку ** с поля * Загрузить открытый ключ на сервер почтовых ключей *

** Шаг 5 **. ** Нажмите ** ** [Отправить] **, чтобы начать генерацию пары ключей:

![](mailvelope-all-en-v01-005.png)

Когда процесс будет завершен, в Mailvelope отобразится: «** Успех! Новый ключ создан и импортирован в менеджер ключей **».

** Шаг 6 **. ** Нажмите ** * Показать ключи *, чтобы взглянуть на новую пару ключей, как показано в разделе ниже.



## 2.2 Экспорт и отправка вашего открытого ключа с помощью Mailvelope

Вы должны поделиться своим открытым ключом с другими, чтобы они могли отправлять вам зашифрованные письма. Вы также должны передать полный «отпечаток» своего ключа через другой канал, чтобы ваши корреспонденты могли убедиться, что открытый ключ, который вы им отправили, действительно принадлежит вам. ** Вы никогда не должны делиться своим закрытым ключом **, так как любой, у кого есть его копия, может расшифровать отправленные вам сообщения и подписать сообщения, чтобы они казались полученными от вас.

Чтобы экспортировать ваш открытый ключ с помощью Mailvelope, выполните следующие действия.

**Шаг 1**. На вкладке браузера ** Параметры Mailvelope ** ** выберите ** вкладку ** Управление ключами **, затем ** нажмите ** ** [Показать ключи] ** слева.

![](mailvelope-all-en-v01-006.png)

**Шаг 2**. ** Нажмите ** ключ, который вы хотите экспортировать. (В нашем случае открытый ключ, который мы только что сгенерировали, - единственный, который у нас есть.)

Это активирует экран ниже:

![](mailvelope-all-en-v01-007.png)

На этом экране отображается, среди прочего, отпечаток вашей пары ключей. Например, отпечаток пары ключей, которую мы только что сгенерировали для *ekaterina@riseup.net*, составляет ** 3B9F 54DD 571A 6F77 251D 92E7 E8B1 F5E6 FBB4 EFFE **.

**Шаг 3**. ** Нажмите ** на ** Экспорт **.

![](mailvelope-all-en-v01-008.png)

** Важно: ** Убедитесь, что ** [Public] ** выбрано в верхней части экрана. Если выбрано * [Private] * или * [Any] *, вы в конечном итоге экспортируете свой закрытый ключ. Вы никогда не должны отправлять свой закрытый ключ другому лицу или загружать его на сервер. (Единственные причины, по которым вы можете захотеть экспортировать свой закрытый ключ, это сделать зашифрованную резервную копию или перенести ваши ключи в новый веб-браузер.) Имя файла по умолчанию должно заканчиваться на «_Pub.asc».

** Шаг 5 **. ** Нажмите ** ** [Сохранить] **, чтобы сохранить ваш открытый ключ

** Шаг 6 **: Отправьте только что экспортированный файл (в данном случае * Elena_Katerina_Pub.asc *) корреспондентам, с которыми вы хотите обменяться зашифрованной электронной почтой.



## 2.3 Импортировать открытый ключ с помощью Mailvelope

Прежде чем вы сможете зашифровать сообщение корреспонденту, вам необходимо импортировать его открытый ключ. Чтобы импортировать открытый ключ корреспондента с помощью Mailvelope, выполните следующие действия.

**Шаг 1**. Получив открытый ключ в виде вложения, сохраните файл где-нибудь на своем компьютере.

**Шаг 2**. На вкладке браузера ** Параметры Mailvelope **, ** выберите ** вкладку ** Управление ключами **, затем ** нажмите ** ** [Импортировать ключи] ** слева.

![](mailvelope-all-en-v01-009.png)

На этом экране вы можете:

- Выполните поиск на сервере открытых ключей, введя имя своего корреспондента, его e-mail адрес или идентификатор ключа.
- Выберите текстовый файл, содержащий ключ
- Скопируйте и вставьте текстовый блок в файл ключа

Приведенные ниже действия предполагают, что вы получили файл ключа и сохранили его на своем компьютере, поэтому мы будем использовать второй вариант.

**Шаг 3**. ** Нажмите ** ** [Выбрать текстовый файл ключа для импорта] **.

** Шаг 4 **. ** Перейдите ** к файлу ключа на вашем компьютере и ** нажмите ** ** [Импорт] **

Когда он будет завершен, Mailvelope отобразит что-то вроде: «** Успех! Открытый ключ 6764717C5D64FBB6 пользователя Mansour <mansour@riseup.net> импортирован в набор ключей **»

Если вы нажмете ** [Показать ключи] **, слева, на вкладке ** Управление ключами **, вы увидите ваш недавно импортированный открытый ключ:

![](mailvelope-all-en-v01-010.png)

Перед отправкой зашифрованного сообщения этому корреспонденту, вы должны проверить его ключ.



## 2.4 Проверка открытого ключа корреспондента

Теперь вы должны убедиться, что ключ, который вы импортировали, на самом деле был получен от человека, которому, по вашему мнению, он принадлежит. Вы и ваши e-mail корреспонденты должны пройти этот процесс для каждого открытого ключа, который вы получаете.

Чтобы проверить открытый ключ вашего корреспондента, свяжитесь с ним, используя средство связи, которое позволяет вам быть абсолютно уверенным, что вы разговариваете с нужным человеком. Личные встречи являются лучшими, но голосовые и видео разговоры приемлемы, если вы уверены, что можете распознать голос или внешний вид. Вы будете обмениваться отпечатками открытого ключа, которые не нужно хранить в тайне, поэтому этот разговор не должен быть конфиденциальным, если вы воздерживаетесь от обсуждения деликатных тем.

И вы, и ваш корреспондент должны проверить отпечатки  открытых ключей, которыми вы обменялись. Отпечаток ключа - это уникальная серия цифр и букв, которая идентифицирует ключ. Вы можете использовать раздел ** Показать ключи ** на вкладке ** [Управление ключами] ** в ** Параметрах Mailvelope **, чтобы определить:

- Отпечаток созданной вами пары ключей
- Отпечаток открытых ключей других людей, которые вы импортировали

Чтобы просмотреть отпечаток определенной пары ключей, выполните следующие действия:

**Шаг 1**. ** Нажмите ** ** [Показать ключи] ** слева на вкладке ** Управление ключами **.

![](mailvelope-all-en-v01-010.png)

**Шаг 2**. ** Кликните ** на ключ, который вы хотите проверить

![](mailvelope-all-en-v01-035.png)

В окне Key Details вы увидите ** отпечаток ** выбранного ключа. Например, ekaterina@riseup.net имеет отпечаток * 3B9F 54DD 571A 6F77 251D 92E7 E8B1 F5E6 FBB4 EFFE *.

Ваш корреспондент также должен выполнить эти шаги. Чтобы проверить отпечатки коючей:

- Прочитайте отпечаток вашей пары ключей вашему корреспонденту,
- Пусть он проверит, что отпечаток его открытого ключа соответствует тому, что вы только что сказали ему,
- Пусть ваш корреспондент прочитает вам отпечаток своего открытого ключа,
- Убедитесь, что отпечаток его открытого ключа соответствует тому, что он только что сказал вам,
- Если отпечатки не совпадают, снова обменяйтесь открытыми ключами и повторите процедуру.

Примечание. Поскольку отпечатки ключей сами по себе не чувствительны, вы можете легко записать отпечаток, который ваш корреспондент зачитывает вам. Затем, когда у вас будет больше времени, вы сможете убедиться, что он соответствует отпечатку его открытого ключа. Именно поэтому некоторые люди печатают свои отпечатки ключей на своих визитных карточках.


## 2.5 Резервное копирование и восстановление всех ваших ключей

Сгенерированная пара ключей и открытые ключи, которые вы собрали и проверили, являются наиболее важным элементом вашей установки Mailvelope. Вы можете сохранить все эти ключи в одном файле для их резервного копирования. См. [Восстановление после потери информации](../../backup), чтобы спланировать стратегию безопасного резервного копирования. Мы рекомендуем обновлять эту резервную копию каждый раз, когда вы генерируете новую пару ключей или импортируете и проверяете важный открытый ключ.

** Важно: ** Поскольку этот файл будет содержать ваш закрытый ключ, вы не должны загружать его на сервер или в какое-либо «облачное хранилище».


** Чтобы сохранить все ваши ключи в одном файле **, выполните следующие действия на вкладке Mailvelope ** Управление ключами **

**Шаг 1**. ** Нажмите ** ** [Показать ключи] **

![](mailvelope-all-en-v01-011.png)

**Шаг 2**. ** Нажмите ** ** [Экспорт] **

![](mailvelope-all-en-v01-012.png)

** Примечание: ** Вы можете выбрать любое имя и местоположение для файла, который будет содержать ваши ключи. В этом примере мы будем использовать имя по умолчанию: ** all_keys.asc **

**Шаг 3**. ** Нажмите ** ** [Сохранить] **

** Шаг 4 **. Сделайте безопасное резервное копирование этого файла, а затем удалите его с вашего компьютера.

** Важно: ** Этот файл содержит ваши закрытые ключи, поэтому вы должны хранить резервную копию в безопасности. Например, вы можете захотеть сохранить его в зашифрованном контейнере VeraCrypt на хорошо спрятанном USB-устройстве хранения данных.

** Чтобы импортировать все ключи в этоn файл **, выполните шаги по сценарию* Импортировать открытый ключ корреспондента * в Разделе 2.3.


# 3. Настройте Mailvelope для работы с вашим сервисом веб-почты

Mailvelope поставляется с предварительно настроенными для работы с несколькими службами веб-почты, включая Gmail. Вы можете проверить, настроен ли Mailvelope для работы с вашим провайдером веб-почты, войдя в свою учетную запись электронной почты и составив новое сообщение. Вы должны увидеть кнопку Mailvelope в правом верхнем углу области сообщения, как показано ниже:

![](mailvelope-all-en-v01-016.png)

Если вы видите эту кнопку, вы можете пропустить остальные шаги в этом разделе.

Чтобы заставить Mailvelope работать с веб-интерфейсом * Roundcube *, используемым [Riseup](https://mail.riseup.net) и другими поставщиками, выполните следующие действия. Следуя аналогичной процедуре, вы также сможете настроить Mailvelop для других провайдеров веб-почты.


**Шаг 1**. ** Запустите ** браузер, в котором вы установили Mailvelope 

**Шаг 2**. ** Войдите ** в свой e-mail аккаунт

**Шаг 3**. ** Перейдите ** на ваш почтовый ящик и нажмите ** открыть ** любое сообщение электронной почты

** Шаг 4 **. ** Нажмите ** значок блокировки Mailvelope на панели инструментов браузера, чтобы открыть меню Mailvelope, как показано ниже

![](mailvelope-all-en-v01-013.png)

** Шаг 5 **. ** Нажмите ** ** [Добавить] **, чтобы отобразить экран, содержащий ** Список поставщиков электронной почты **

![](mailvelope-all-en-v01-014.png)

Внизу этого списка вы должны увидеть новую запись для ** mail.riseup.net **.

** Шаг 6 **. Вернитесь на вкладку браузера с вашей веб-почтой.

** Шаг 7 **. ** Нажмите «Создать» **, чтобы написать новое электронное письмо.

** Шаг 8 **. ** Нажмите ** значок блокировки Mailvelope на панели инструментов браузера, чтобы открыть меню Mailvelope, как показано ниже

![](mailvelope-all-en-v01-015.png)

** Шаг 8 **. ** Нажмите ** ** [Добавить] ** еще раз.

Ваш браузер снова отобразит экран, содержащий ** Список поставщиков электронной почты **.

** Шаг 9 **. ** Закройте ** эту вкладку браузера и вернитесь к своей веб-почте.

** Шаг 10 **. ** Перезагрузите ** страницу, на которой вы пишете новое письмо.

Вы должны увидеть кнопку Mailvelope в правом верхнем углу области сообщения, как показано ниже:

![](mailvelope-all-en-v01-016.png)


# 4. Шифрование и дешифрование сообщений и файлов

После обмена ключами и проверки того, что Mailvelope настроен для работы с вашим провайдером веб-почты, вы можете начать шифрование и дешифрование сообщений.

Для объяснения того, как работает Mailvelope, см. раздел [Вещи, которые вы должны знать об этом инструменте, прежде чем начать](#things-you-should-know-about-mailvelope-before-you-start) выше. И имейте в виду, что Mailvelope защищает только * содержание * сообщений и вложений. ** Следующая информация никогда не шифруется: **

- Строка * Тема: *
- E-mail адрес отправителя
- E-mail адреса получателей
- Имена файлов вложений
- Любые реальные имена, которые могут быть связаны с отправителями и получателями («** Елена С. Катерина **», например, по следующему e-mail адресу: «** Елена С. Катерина <ekaterina@riseup.net> **»)

Поэтому тщательно выбирайте темы писем и подумайте о создании пары ключей как минимум для одного e-mail аккаунта, в котором не указано ваше настоящее имя.

Наконец, когда вы отправляете зашифрованное письмо, будьте уверены, что копия, зашифрованная на ваш открытый ключ, будет помещена в папку «Отправленные».



## 4.1 Шифрование сообщений с помощью Mailvelope

Используя браузер, в котором вы установили Mailvelope, войдите в учетную запись веб-почты, с которой был настроен Mailvelope, затем начните писать новое сообщение и выполните следующие действия:

**Шаг 1**. Заполните поля ** Кому: **, ** Копия: ** и ** Тема: **, как обычно:

![](mailvelope-all-en-v01-017.png)

** Примечание: ** Если вы не видите кнопку Mailvelope в верхнем правом углу области сообщений, обратитесь к разделу * Настройка Mailvelope для работы с вашим провайдером веб-почты * выше.

**Шаг 2**. ** Нажмите ** кнопку Mailvelope в верхнем правом углу области сообщения, чтобы открыть окно Mailvelope ** Написать письмо **.

![](mailvelope-all-en-v01-018.png)

**Шаг 3**. ** Введите ** ваше сообщение.

** Важно: ** * Если вы намереваетесь зашифровать сообщение, вы должны ввести его в специальное окно ** Создать почту **, а не в обычную текстовую область, отображаемую вашим интерфейсом веб-почты. * В противном случае, ваш поставщик веб-почты может записывать незаконченные черновики, как вы печатаете, без вашего ведома.

Все адреса электронной почты в полях ** Кому: **, ** Копия: ** и ** Скрытая копия: ** будут скопированы в поле * Получатели * окна Mailvelope * Создать электронную почту *. Ваше сообщение будет зашифровано для всех открытых ключей, связанных с указанными здесь адресами (а также для вашего собственного открытого ключа). Вы можете вручную добавить или удалить адрес в окне * Написать письмо *. Если какой-либо из этих адресов ** помечен красным **, это означает, что у вас нет открытого ключа для этого получателя, и вы не сможете отправить сообщение, если вы не удалите этого получателя или не получите его открытый ключ.

** Примечание: ** Из-за способа работы OpenPGP не следует полагаться на поле ** Скрытая копия **, чтобы скрыть существование некоторых получателей от других получателей.

**Шаг 3**. Когда вы закончите выбирать получателей и составлять ваше сообщение, ** нажмите [Зашифровать] **. Ваше сообщение будет зашифровано и перенесено в обычную область сообщений вашей веб-почты.

![](mailvelope-all-en-v01-019.png)

** Шаг 4 **. ** Нажмите [Отправить] **.


## 4.2 Расшифровка сообщений с помощью Mailvelope

Используя браузер, в котором вы установили Mailvelope, войдите в учетную запись веб-почты, с которой был настроен Mailvelope, откройте зашифрованное сообщение, отправленное вам, и выполните следующие действия:

Mailvelope автоматически обнаружит, зашифровано ли входящее сообщение. Он будет отображать значок Mailvelope поверх зашифрованного сообщения, как показано ниже

![](mailvelope-all-en-v01-020.png)

**Шаг 1**. ** Нажмите ** значок Mailvelope, чтобы активировать экран пароля.

**Шаг 2**. ** Введите ** пароль, который вы выбрали при создании пары ключей

![](mailvelope-all-en-v01-021.png)

** Важно: ** Если вы установите флажок * Запомнить пароль временно *, Mailvelop запомнит ваш пароль на 30 минут. (Вы можете изменить этот промежуток времени в настройках Mailvelope.) Мы рекомендуем снять этот флажок, если вы не собираетесь расшифровывать много сообщений.

**Шаг 3**. ** Нажмите ** ** [OK] **, чтобы расшифровать сообщение

![](mailvelope-all-en-v01-022.png)

** Примечание: ** Если в Mailvelope отображается сообщение «* Ошибка! Не найден закрытый ключ для этого сообщения *, это означает, что отправитель не зашифровал это сообщение на ваш открытый ключ (и даже может не * иметь * вашего открытого ключа). Вы не сможете расшифровать сообщение. Свяжитесь с отправителем и попросите ее повторно отправить зашифрованное сообщение на ваш ключ. Вы также можете отправить ему свой ключ и предложить проверить его отпечаток ключа.

** Важно **: Как правило, не рекомендуется делать незашифрованные копии зашифрованных сообщений или вложений и сохранять их на своем компьютере.

## 4.3 Подпись сообщений и проверка подписей с помощью Mailvelope

В дополнение к шифрованию сообщений на чужой открытый ключ, Mailvelop может * подписать * их, используя ваш личный ключ. Таким образом, получатели, имеющие ваш открытый ключ, могут проверить, что конкретное сообщение действительно пришло от вас и не было изменено при передаче.

В настоящее время Mailvelope не позволяет подписывать и шифровать одно и то же сообщение.


### 4.3.1 Подпись сообщения

Чтобы подписать сообщение, выполните следующие действия.

**Шаг 1**. Создайте сообщение в окне * Создать E-Mail * Mailvelope, как показано ниже:

![](mailvelope-all-en-v01-029.png)

**Шаг 2**. ** Нажмите ** ** [Подписать] **.

![](mailvelope-all-en-v01-030.png)

**Шаг 3**. ** Выберите ** закрытый ключ, который будет использоваться при подписании сообщения.

** Шаг 4 **. ** Нажмите ** ** [OK] **.

** Шаг 5 **. ** Введите ** кодовую фразу для ключа, который вы выбрали.

![](mailvelope-all-en-v01-031.png)

Обратите внимание, что мы отменили выбор опции * Запомнить пароль временно *.

** Шаг 6 **. ** Нажмите ** ** [OK] **.

Подписанное сообщение будет скопировано в область сообщений вашей веб-почты, как показано ниже:

![](mailvelope-all-en-v01-032.png)

** Важно: ** Когда вы подписываете письмо, оно не будет зашифровано. Обратите внимание, что вы все еще можете прочитать содержание сообщения выше. Блок текста * ниже * сообщения является цифровой подписью. Не редактируйте сообщение перед отправкой. В противном случае получателям сообщат, что ваша подпись недействительна.

** Шаг 7 **. ** Нажмите ** ** [Отправить] **.



### 4.3.2 Проверка подписанного сообщения

Чтобы проверить подписанное сообщение, выполните следующие действия при просмотре сообщения.

![](mailvelope-all-en-v01-033.png)

**Шаг 1**. ** Нажмите ** конверт с красной печатью, которая отображается над сообщением.

Если у вас есть открытый ключ для этого отправителя, над сообщением должно появиться зеленое поле, чтобы вы знали, что оно * подписано * соответствующим закрытым ключом и не было изменено при передаче.

![](mailvelope-all-en-v01-034.png)

** Важно: ** Если вы видите красное поле с надписью * Неверная подпись *, возможно, сообщение было подделано или отправлено кем-то другим. Вам следует связаться с человеком в поле ** От: **, используя другой канал связи, и подтвердить, что он сам отправил его.

Если вы видите желтое поле с надписью * Подписано неизвестным ключом *, это означает, что у вас нет открытого ключа, соответствующего закрытому ключу, используемому для подписи сообщения. Вы не сможете проверить подпись, пока не получите и не подтвердите правильный открытый ключ.

## 4.4 Шифрование и дешифрование файлов с помощью Mailvelope

Mailvelope также может зашифровать и расшифровать файлы. Зашифрованные файлы могут быть прикреплены к e-mail сообщениям.

### 4.4.1 Шифрование и вложение файлов

Чтобы зашифровать файл, выполните следующие действия, используя браузер, в котором вы установили Mailvelope.

**Шаг 1**. ** Нажмите ** значок блокировки Mailvelope на панели инструментов браузера и ** выберите ** ** Параметры **, чтобы открыть вкладку браузера ** Параметры Mailvelope **.

**Шаг 2**. ** Выберите ** вкладку ** [Шифрование файла] **.

**Шаг 3**. ** Нажмите ** ** Шифрование ** на левой стороне.

** Шаг 4 **. ** Нажмите ** ** [+ Добавить] **, чтобы выбрать файлы, которые вы хотите зашифровать, как показано ниже.

![](mailvelope-all-en-v01-023.png)

В этом примере мы выбрали файл изображения с именем * picture.png *. Вы можете добавить более одного файла. Каждый из них будет зашифрован отдельно от выбранных вами открытых ключей.

** Шаг 5 **. **Нажмите кнопку** **[Далее]**.

![](mailvelope-all-en-v01-024.png)

** Шаг 6 **. ** Выберите ** основного получателя, для которого вы хотите зашифровать выбранные файлы.

** Шаг 7 **. ** Нажмите ** ** [Добавить] **.

В этом примере мы выбираем ключи как для Елены, так и для Мансура. ** Вы можете выбрать более одного человека, включая себя. **

** Шаг 8 **. ** Нажмите ** ** [Шифровать] **.

![](mailvelope-all-en-v01-025.png)

** Шаг 9 **. ** Нажмите ** ** [Сохранить все] **, чтобы сохранить зашифрованные файлы.

Зашифрованные файлы будут сохранены в том месте, куда ваш браузер сохраняет загруженные файлы (скорее всего, в папке * Downloads *). Зашифрованные файлы будут иметь новое расширение * .asc *. Например, * picture.png * станет * picture.png.asc *. Теперь вы можете отправлять зашифрованные файлы как вложения, используя обычную функцию вложения вашего веб-провайдера.

** Важно: ** Имейте в виду, что на вашем компьютере все еще есть незашифрованная версия, поэтому обязательно отправьте зашифрованную версию (ту, которая заканчивается на * .asc *). Также помните, что * исходное имя файла все еще отображается * и не будет зашифровано. Поэтому выбирайте имя, которое не раскрывает конфиденциальную информацию.



### 4.4.2 Расшифровка файлов

Чтобы расшифровать файл, выполните следующие действия. Если зашифрованный файл был отправлен вам как вложение, эти шаги предполагают, что вы уже сохранили его где-то на вашем компьютере.

**Шаг 1**. ** Нажмите ** значок блокировки Mailvelope на панели инструментов браузера и ** выберите ** ** Параметры **, чтобы открыть вкладку браузера ** Параметры Mailvelope **.

**Шаг 2**. ** Выберите ** вкладку ** [Шифрование файла] **

**Шаг 3**. ** Нажмите ** ** Расшифровка ** на левой стороне.

** Шаг 4 **. ** Нажмите ** ** [Добавить] ** и выберите файл, который вы хотите расшифровать.

![](mailvelope-all-en-v01-026.png)

Вы можете выбрать несколько зашифрованных файлов, если они все были зашифрованы с использованием одного и того же открытого ключа.

** Шаг 5 ** ** Нажмите ** ** [Далее] **.

** Шаг 6 **. ** Введите ** кодовую фразу для вашего закрытого ключа.

![](mailvelope-all-en-v01-027.png)

Обратите внимание, что мы отменили выбор опции * Запомнить пароль временно *.

** Шаг 7 **. ** Нажмите ** ** [OK] **.

![](mailvelope-all-en-v01-028.png)

** Шаг 8 **. ** Нажмите ** ** [Сохранить все] **, чтобы сохранить расшифрованные файлы.

Зашифрованные файлы будут сохранены в том месте, куда ваш браузер сохраняет загруженные файлы (скорее всего, в папке * Downloads *).



# FAQ

** Q **: Можно ли установить Mailvelope в разных браузерах, таких как Safari или Opera?

** A **: Нет. В настоящее время Mailvelope работает только как надстройка / расширение в браузерах ** Mozilla Firefox ** и ** Google Chrome или Chromium **.

** Q **: для скольких аккаунтов я могу сгенерировать пары ключей?

** A **: столько, сколько вам нужно.

** Q **: Mailvelop хранит мои личные ключи где-нибудь в сети (например, в облаке)?

** A **: Нет, закрытые ключи хранятся на вашем компьютере. Для ** Firefox ** они находятся в каталоге профиля, для ** Chrome или Chromium ** это каталог пользовательских данных. Однако открытые ключи могут быть загружены на сервер ключей Mailvelope.

** Q **: Позволяет ли Mailvelop создавать ключи, которые могут работать только в течение ограниченного времени?

** A **: В данный момент это невозможно.

** Q **: Можно ли установить Mailvelope для портативной версии браузера?

** A **: Да. Как только вы это сделаете, вы можете скопировать папку браузера, которая содержит установочную программу Mailvelope и все ключи, на USB и использовать ее на другом компьютере.