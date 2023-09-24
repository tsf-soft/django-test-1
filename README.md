# Подключение Яндекс Диска в качестве сетевого диска компьютера

<br/>

## 1. Общие сведения

### О чём здесь пойдёт речь

Яндекс Диск - это облачный сервис, позволяющий хранить файлы в облачной инфрастуктуре созданной и поддерживаемой компанией Яндекс.
Используя этот сервис вы сможете работать с файлами размещаемыми на нём - с любого устройства подключенного к сети интернет.
Подробнее о возможностях предоставляемых сервисом можно узнать [здесь](https://360.yandex.ru/disk/).

Для большего удобства в работе с сервисом, Яндекс Диск может быть подключен к персональному компьютеру как обычный сетевой диск компьютера.
Подключив Яндекс Диск к своему компьютеру таким образом, - вы сможете средствами операционной системы выполнять с ним те же действия что и с любым другим дисковым накопителем, имеющимся в вашем компьютере.

Превратить облачный сервис в "обычный диск", позволяет протокол [WebDAV](https://ru.wikipedia.org/wiki/WebDAV).


### Прежде чем начать

<a name="acc_create"></a>

Для того чтобы начать пользоваться сервисом Яндекс Диск, нужно быть зарегистрированным в Яндекс через аккаунт **Яндекс ID**.
Если вы ещё не зарегистрированы в Яндекс, то вам нужно зарегистрировать свой аккаунт **Яндекс ID**. Подробнее о том, как это сделать сказано [здесь](https://yandex.ru/support/id/authorization/registration.html).
Вопросы безопасности связанные с регистируемым аккаунтом касающиеся требований к паролям, в том числе для доступа к Яндекс Диску, подробно описаны в [этой статье](https://yandex.ru/support/id/authorization/app-passwords.html).

Дополнительно акцентирую ваше внимание на факторе безопасности касающимся возможности использования сервиса Яндекс Диск сторонним программным обеспечением (ПО). Сторонним ПО в данном случае является протокол [WebDEV](https://ru.wikipedia.org/wiki/WebDAV). Вам не удастся подключить Яндекс Диск в качестве сетевого диска из-за проблем с доступом (<a href="#fig11">рис. 1.1</a>), если вы не установите индивидуальный пароль для приложения Яндекс Диск.

<a name="fig11"></a>

![Не возможно подключиться](https://github.com/tsf-soft/django-test-1/assets/6228605/3de343fe-8cb3-4661-9278-6f49e10ec005)
_<p>Рисунок 1.1. Отсутствие доступа при не установленном индивидуальном пароле для приложения</p>_

<br/>

Для установки индивидуального пароля на приложение Яндекс Диск, в Яндекс ID вам нужно последовательно выбрать следующие пункты меню: _"Управление аккаунтом" --> "Безопасность" --> "Пароли приложений" --> "Файлы (WebDAV)"_ (<a href="#fig12">рис. 1.2</a>).

<a name="fig12"></a>

![Место установки индивидуального пароля](https://github.com/tsf-soft/django-test-1/assets/6228605/d0a9a10e-53da-4974-b810-996d1b0006f2)
_<p>Рисунок 1.2. Последовательность элементов меню в Яндекс ID</p>_

<br/>

Нажав на последний элемент меню (п.3 на рис. 1.2) вы получите форму с предложением придумать новый пароль для приложения. Эта форма состоит из двух вкладок. На первой вкладке (<a href="#fig13">рис. 1.3</a>) вам будет предложено придумать имя для пароля. Сам пароль вы получите на второй вкладке (<a href="#fig14">рис. 1.4</a>) нажав на кнопку "Далее".

<a name="fig13"></a>

![Ввод имени пароля приложения](https://github.com/tsf-soft/django-test-1/assets/6228605/10a9b82e-28cc-44b4-b398-69455daf7947)
_<p>Рисунок 1.3. Вкладка №1 формы создания пароля приложения</p>_

<br/>

<a name="fig14"></a>

![Собственно пароль приложения](https://github.com/tsf-soft/django-test-1/assets/6228605/926cf735-583e-408d-ba46-97989118c3f2)
_<p>Рисунок 1.4. Вкладка №2 формы создания пароля приложения</p>_

<br/>

В случае успешного создания вами индивидуального пароля для приложения в **Яндекс ID**, - на ваш адрес электроной почты от службы поддержки Яндекс ID, придёт письмо с уведомлением о совершенном действии (<a href="#fig15">рис. 1.5</a>)

<a name="fig15"></a>

![Уведомление от службы поддержки](https://github.com/tsf-soft/django-test-1/assets/6228605/1d53ba70-f1c1-4379-8672-8a5a19f2b426)
_<p>Рисунок 1.5. Письмо-уведомление от службы поддержки Яндекс ID</p>_

<br/>

Созданный вами индивидуальный пароль для приложения храниться в Яндекс ID в зашифрованном виде. Код пароля, в т.ч. в случае вашего обращения в службу поддержки, вы можете посмотреть открыв пункт с именем созданного вами пароля (<a href="#fig16">рис. 1.6</a>).

<a name="fig16"></a>

![Хранение индивидуального пароля в системе](https://github.com/tsf-soft/django-test-1/assets/6228605/d0680ab8-e0c3-4394-aaa6-81ef2b78d956)
_<p>Рисунок 1.6. Хранение индивидуального пароля приложения в Яндекс ID</p>_

<br/>

Теперь, имея аккаунт **Яндекс ID** с отдельно установленным паролем для приложения Яндекс Диск, можно приступить к подключению сервиса Яндекс Диск в качестве сетевого диска к персональному компьютеру. В зависимости от используемой вами операционной системы последовательность действий по достижению этой цели будет различной. Здесь рассмотрены варианты подключения сервиса к персональным компьютерам с операционными системами <a href="#con_windows">**Windows**</a> и **Linux Ubuntu**, причём для OS Linux рассмотрены два варианта: **Linux Ubuntu GUI** и **Linux Ubuntu CLI**.

<br/>

<a name="con_windows"></a>

## 2. Подключение Яндекс Диска в OS Windows

В операционной системе Windows нужно сделать следующее:

### 2.1. Воспользоваться проводником Windows

В проводнике Windows вам нужно выбрать значок `Этот компьютер`. Далее выполнить один из вариантов: либо вызвать контекстное меню (<a href="#fig21">рис. 2.1</a>), содержащее нужный пункт  `Подключить сетевой диск...` путём нажатия правой кнопки мыши, либо в главном меню проводника (<a href="#fig22">рис. 2.2</a>) выбрать на ленте инструментов элемент `Подключить сетевой диск`.

<a name="fig21"></a>

![Выбор из контекстного меню](https://github.com/tsf-soft/django-test-1/assets/6228605/1e83e011-00c9-4ad0-9055-5f187721ac7e)
_<p>Рисунок 2.1. Контекстное меню элемента "Мой компьютер"</p>_

<br/>

<a name="fig22"></a>

![Выбор из панели инструментов проводника](https://github.com/tsf-soft/django-test-1/assets/6228605/17ce573e-254e-477d-9de9-1510ffa22e6f)
_<p>Рисунок 2.2. Панель инструментов проводника для элемента "Мой компьютер"</p>_

<br/>

### 2.2. Ввести данные в форму "Подключение сетевого диска"

Поля открывшейся формы `Подключение сетевого диска` (<a href="#fig23">рис. 2.3</a>) нужно установить таким образом:

- в поле `Диск` - выбрать один из предлагаемых системой свободных символов, который будет назначен смонтированному сетевому диску;
- в поле `Папка` - установить `https://webdav.yandex.ru`;
- чекбокс `Восстанавливать подключение при входе в систему` - нужен для обеспечения постоянной доступности сетевого диска, в т.ч. после перезагрузки; значение по умолчанию `true` (установлен);
- чекбокс `Использовать другие учётные данные` - нужен для ввода учётных данных, отличных от сохранённых по умолчанию для полей формы (позволяет войти в другой аккаунт <a href="#acc_create">Яндекс ID</a>; значение по умолчанию `false` (не установлен).

> [!NOTE]
> _**Примечание:**
> При не установленном чекбоксе `Использовать другие учётные данные` <a href="#cred_frm">учётные данные</a> запрошены не будут; вход будет выполнен со значениями учётных данных, сохранённых по умолчанию ранее._

<br/>

<a name="fig23"></a>

![Форма "Подключение сетевого диска"](https://github.com/tsf-soft/django-test-1/assets/6228605/dd612dbe-7af3-4f7d-bc36-d5ae9dff8eba)
_<p>Рисунок 2.3. Форма "Подключение сетевого диска"</p>_

<br/>

<a name="cred_frm"></a>

### 2.3. Ввести ваши учётные данные

Открывшаяся форма `Безопасность Windows` (<a href="#fig24">рис. 2.4</a>) потребует от вас ввести учётные данные:

- в поле `Имя пользователя` - нужно ввести ваш логин, который вы задали при создании <a href="#acc_create">аккаунта</a> **Яндекс ID**;
- в поле `Пароль` - введите <a href="#fig13">индивидуальный пароль приложения</a>, установленный вами в аккаунте для приложения Яндекс Диск;
- чекбокс `Запомнить учетные данные` - отвечает за автоматическое последующее заполнение первых двух полей введёнными вами данными, в случае его выбора; значение по умолчанию `false` (не установлен).

<a name="fig24"></a>

![Форма "Безопасность Windows"](https://github.com/tsf-soft/django-test-1/assets/6228605/d41adc37-e829-4851-8517-1c56768b070d)
_<p>Рисунок 2.4. Форма "Безопасность Windows"</p>_

<br/>

### 2.4. Оценить полученный результат

В результате проделанных действий по подключению сервиса Яндекс Диск, в разделе проводника "Сеть" появиться новое защищённое подключение к сетевому компьютеру (<a href="#fig25">рис. 2.5</a>), а также новый подключенный сетевой диск (<a href="#fig26">рис. 2.6</a>)

<a name="fig25"></a>

![Защищённое подключение к сетевому компьютеру](https://github.com/tsf-soft/django-test-1/assets/6228605/91000b0c-0795-48d6-97f3-713c087973f9)
_<p>Рисунок 2.5. Раздел "Сеть" проводника Windows</p>_

<br/>

<a name="fig26"></a>

![Подключенный сетевой диск](https://github.com/tsf-soft/django-test-1/assets/6228605/0162539c-9c13-4c54-8050-8bd491c0f0ad)
_<p>Рисунок 2.6. Подключенный сетевой диск и его содержимое</p>_

<br/>

> [!NOTE]
> _**Примечание:**
> На рис.2.6 показано уже переименованное, короткое наименование `диска Z` (идентификатор YD). Эта операция выполнена из контекстного меню "Переименовать"._

<br/>

<a name="con_linux_gui"></a>

## 3. Подключение Яндекс Диска в OS Linux Ubuntu (GUI)

Здесь аббревиатура [GUI](https://ru.wikipedia.org/wiki/Графический_интерфейс_пользователя) (graphical user interface) - графический интерфейс пользователя, означает что операционная система имеет оконнный графический интерфейс интуитивно похожий на Windows. Одним из распространённых вариантов GUI для Linux-подобных операционных систем, является GUI [GNOME](https://ru.wikipedia.org/wiki/GNOME).

Для подключения Яндекс Диска как сетевого устройства по протоколу WebDAV к DeskTop версии Linux Ubuntu с графической оболочной GNOME нужно выполнить такие шаги:

### 3.1. Открыть приложение "Файлы"

На панели инструментов GUI нажмите на соответствующий значёк (на <a href="#fig31">рис. 3.1</a> значёк обведен красной рамкой). Все дальнейшие действия по подключению Яндекс Диска к компьютеру в этой операционной системе, будем проводить с использованием открывшегося окна приложения "Файлы".

<a name="fig31"></a>

![Приложение "Файлы" Gnome Linux](https://github.com/tsf-soft/django-test-1/assets/6228605/0e19858d-f94a-406e-a707-758a907c33e9)
_<p>Рисунок 3.1. Приложение "Файлы" GNOME Linux</p>_

### 3.2. Выбрать поле "Подключение к серверу"

Внизу "Панели расположений" приложения "Файлы" (рис. 3.2), выберите  пункт `+ Другие места`.

![Доступные метоположения файлов на компьютере](https://github.com/tsf-soft/django-test-1/assets/6228605/3d6e7f2f-2b6d-4c83-8621-805e4ec9711d)
_<p>Рисунок 3.2. Доступные местоположения файлов на компьютере</p>_

### 3.3. Ввсести адрес сервера

В поле "Подключится к серверу", введите адрес сервера в формате:

'''bash

davs://<Имя вашего <a href="#acc_create">аккаунта</a>>@webdav.yandex.ru

'''



