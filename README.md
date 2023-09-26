# Подключение Яндекс Диска в качестве сетевого диска компьютера

<br/>

## 1. Общие сведения

### 1.1. О чём здесь пойдёт речь

Яндекс Диск - это облачный сервис, позволяющий хранить файлы в облачной инфрастуктуре созданной и поддерживаемой компанией Яндекс.
Используя этот сервис вы сможете работать с размещаемыми на нём файлами используя любое устройство подключенное к сети интернет.
Подробнее о возможностях предоставляемых сервисом можно узнать [здесь](https://360.yandex.ru/disk/).

Для большего удобства в работе с сервисом, Яндекс Диск можно подключить к персональному компьютеру как обычный сетевой диск компьютера.
Подключив Яндекс Диск к своему компьютеру таким образом, вам будут доступны все действия выполняемые над ним средствами операционной системы как с любым другим дисковым накопителем, имеющимся в вашем компьютере.

Превратить облачный сервис в "обычный диск", позволяет протокол [WebDAV](https://ru.wikipedia.org/wiki/WebDAV).

Вопросам подключения сервиса Яндекс Диск в качестве сетевого диска компьютера в различных операционных системах будут посвящены дальнейшие разделы этого руководства.

### 1.2. Прежде чем начать

<a name="acc_create"></a>

Для того чтобы начать пользоваться сервисом Яндекс Диск, нужно быть зарегистрированным в Яндекс через аккаунт сервиса **Яндекс ID**.
Если вы ещё не зарегистрированы в Яндекс, то вам нужно зарегистрировать свой аккаунт **Яндекс ID**. Подробнее о том, как это сделать сказано [здесь](https://yandex.ru/support/id/authorization/registration.html).
Вопросы безопасности связанные с регистируемым аккаунтом касающиеся требований к паролям, в том числе для доступа к Яндекс Диску, подробно описаны в [этой статье](https://yandex.ru/support/id/authorization/app-passwords.html).

Дополнительно акцентирую ваше внимание на факторе безопасности касающемся возможности использования сервиса Яндекс Диск сторонним программным обеспечением (ПО). Сторонним ПО в данном случае является протокол [WebDEV](https://ru.wikipedia.org/wiki/WebDAV). Вам не удастся подключить Яндекс Диск в качестве сетевого диска из-за проблем с доступом (<a href="#fig11">рис. 1.1</a>), если вы не установите индивидуальный пароль для приложения Яндекс Диск.

<a name="fig11"></a>

![Не возможно подключиться](https://github.com/tsf-soft/django-test-1/assets/6228605/3de343fe-8cb3-4661-9278-6f49e10ec005)
_<p>Рисунок 1.1. Отсутствие доступа при не установленном индивидуальном пароле для приложения</p>_

<br/>

Для установки индивидуального пароля на приложение Яндекс Диск, в сервисе **Яндекс ID** вам нужно последовательно выбрать следующие пункты меню: "**Управление аккаунтом**" --> "**Безопасность**" --> "**Пароли приложений**" --> "**Файлы (WebDAV)**" (<a href="#fig12">рис. 1.2</a>).

<a name="fig12"></a>

![Место установки индивидуального пароля](https://github.com/tsf-soft/django-test-1/assets/6228605/d0a9a10e-53da-4974-b810-996d1b0006f2)
_<p>Рисунок 1.2. Последовательность элементов меню в Яндекс ID</p>_

<br/>

Нажав на последний элемент меню (п.3 на рис. 1.2) вы получите форму с предложением придумать новый пароль для приложения. Эта форма состоит из двух вкладок. На первой вкладке (<a href="#fig13">рис. 1.3</a>) вам будет предложено придумать имя для пароля. Сам пароль вы получите на второй вкладке (<a href="#fig14">рис. 1.4</a>) нажав на кнопку "**Далее**".

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

Теперь, имея аккаунт **Яндекс ID** с отдельно установленным паролем для приложения Яндекс Диск, можно приступить к подключению сервиса Яндекс Диск в качестве сетевого диска к персональному компьютеру.

В зависимости от используемой вами операционной системы вы будете использовать различные инструменты подключения. В рамках этого руководства последовательность действий по подключению Яндекс Диска в качестве сетевого диска сведена к четырём пунктам. Здесь рассмотрены варианты подключения сервиса к персональным компьютерам с операционными системами <a href="#con_windows">**Windows**</a> и **Linux Ubuntu**, причём для OS Linux рассмотрены два варианта: <a href="#con_linux_gui">**Linux Ubuntu GUI**</a> и <a href="#con_linux_cli">**Linux Ubuntu CLI**</a>.

<br/>

<a name="con_windows"></a>

## 2. Подключение Яндекс Диска в OS Windows

В операционной системе Windows для подключения сервиса Яндекс Диск в качестве сетевого диска персонального компьютера нужно выполнить следующую последовательность действий:
- <a href="#chapt_21">использовать в качестве инструмента подключения проводник Windows</a>;
- <a href="#chapt_22">установить параметры сетевого подключения к сервису</a>;
- <a href="#chapt_23">авторизоваться на сервисе Яндекс Диск</a>;
- <a href="#chapt_24">оценить полученный результат</a>.

Далее подробно о каждом шаге.

### 2.1. Проводник Windows, как инструмент подключения

<a name="chapt_21"></a>

Для подключения сервиса Яндекс Диск в качестве сетеводго диска, в проводнике Windows нужно выбрать значок "**Этот компьютер**". Далее необходимо выполнить одно из действий:
- либо вызвать контекстное меню (<a href="#fig21">рис. 2.1</a>), содержащее нужный пункт  "**Подключить сетевой диск...**" путём нажатия правой кнопки мыши;
- либо в главном меню проводника (<a href="#fig22">рис. 2.2</a>) выбрать на ленте инструментов элемент "**Подключить сетевой диск**".

<a name="fig21"></a>

![Выбор из контекстного меню](https://github.com/tsf-soft/django-test-1/assets/6228605/1e83e011-00c9-4ad0-9055-5f187721ac7e)
_<p>Рисунок 2.1. Контекстное меню элемента "Мой компьютер"</p>_

<br/>

<a name="fig22"></a>

![Выбор из панели инструментов проводника](https://github.com/tsf-soft/django-test-1/assets/6228605/17ce573e-254e-477d-9de9-1510ffa22e6f)
_<p>Рисунок 2.2. Панель инструментов проводника для элемента "Мой компьютер"</p>_

Выполнение этого действия приведёт к открытию формы "**Подключение сетевого диска**" (<a href="#fig23">рис. 2.3</a>).

<br/>

### 2.2. Установка параметров подключения к сервису

<a name="chapt_22"></a>

Поля открывшейся формы "**Подключение сетевого диска**" (<a href="#fig23">рис. 2.3</a>) нужно установить таким образом:

- в поле "**Диск**" - выбрать один из предлагаемых системой свободных символов, который будет назначен смонтированному сетевому диску;
- в поле "**Папка**" - установить `https://webdav.yandex.ru`;
- чекбокс "**Восстанавливать подключение при входе в систему**" - нужен для обеспечения постоянной доступности сетевого диска, в т.ч. после перезагрузки операционной системы; значение по умолчанию `true` (установлен);
- чекбокс "**Использовать другие учётные данные**" - нужен для ввода учётных данных, отличных от сохранённых по умолчанию для полей формы (позволяет войти в другой аккаунт <a href="#acc_create">Яндекс ID</a>); значение по умолчанию `false` (не установлен).

> [!NOTE]
> _**Примечание:**
> При не установленном чекбоксе "**Использовать другие учётные данные**" <a href="#cred_frm">учётные данные</a> запрошены не будут; вход будет выполнен автоматически со значениями учётных данных по умолчанию, т.е. учётных данных сохраненных ранее._

<br/>

<a name="fig23"></a>

![Форма "Подключение сетевого диска"](https://github.com/tsf-soft/django-test-1/assets/6228605/dd612dbe-7af3-4f7d-bc36-d5ae9dff8eba)
_<p>Рисунок 2.3. Форма "Подключение сетевого диска"</p>_

<br/>

<a name="cred_frm"></a>

### 2.3. Авторизация на сервисе

<a name="chapt_23"></a>

Открывшаяся форма "**Безопасность Windows**" (<a href="#fig24">рис. 2.4</a>) потребует от вас ввести учётные данные:

- в поле "**Имя пользователя**" - нужно ввести ваш логин, который вы задали при создании <a href="#acc_create">аккаунта</a> **Яндекс ID**;
- в поле "**Пароль**" - введите <a href="#fig13">индивидуальный пароль приложения</a>, установленный вами в аккаунте для приложения Яндекс Диск;
- чекбокс "**Запомнить учетные данные**" - отвечает за автоматическое последующее заполнение первых двух полей ранее введёнными вами данными в случае его выбора; значение по умолчанию `false` (не установлен).

<a name="fig24"></a>

![Форма "Безопасность Windows"](https://github.com/tsf-soft/django-test-1/assets/6228605/d41adc37-e829-4851-8517-1c56768b070d)
_<p>Рисунок 2.4. Форма "Безопасность Windows"</p>_

<br/>

### 2.4. Оценка полученного результата

<a name="chapt_24"></a>

В результате выполненной последовательности действий по подключению сервиса Яндекс Диск, в разделе проводника "**Сеть**" появиться новое защищённое подключение к сетевому компьютеру (<a href="#fig25">рис. 2.5</a>), а также новый подключенный сетевой диск (<a href="#fig26">рис. 2.6</a>)

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
> На рис.2.6 показано уже переименованное, короткое наименование `диска Z` (идентификатор **YD**). Эта операция выполнена из элемента "Сетевой диск Z", путём использования контекстного меню содержащего элемент  "**Переименовать**"._

Выбранный на <a href="#fig26">рис. 2.6</a> файл _"Москва.jpg"_ будет реперным элементом в рамках этого руководства. Наличие этого файла в каталоге сетевого диска будет свидетельствовать о том, что подключение выполнено к одному и тому же экземпляру Яндекс Диска при использовании вариантов подключения с использованием различных операционных систем.

<br/>

<a name="con_linux_gui"></a>

## 3. Подключение Яндекс Диска в OS Linux Ubuntu (GUI)

Здесь аббревиатура [GUI](https://ru.wikipedia.org/wiki/Графический_интерфейс_пользователя) (graphical user interface) означает, что операционная система имеет оконнный графический интерфейс интуитивно похожий на Windows. Одним из распространённых вариантов GUI для Linux-подобных операционных систем, является GUI [GNOME](https://ru.wikipedia.org/wiki/GNOME).

Для подключения Яндекс Диска как сетевого устройства по протоколу WebDAV к персональному компьютеру с DeskTop версией Linux Ubuntu имеющей графическую оболочку GNOME нужно выполнить такие шаги:
- <a href="#chapt_31">использовать в качестве инструмента подключения приложение "**Файлы**" среды GNOME</a>;
- <a href="#chapt_32">установить параметры сетевого подключения к сервису</a>;
- <a href="#chapt_33">подключиться к сервису Яндекс Диска</a>;
- <a href="#chapt_24">оценить полученный результат</a>.

Далее подробно о каждом шаге.

### 3.1. Приложение "**Файлы**", как инструмент подключения

<a name="chapt_31"></a>

На панели инструментов GUI нужно нажать на соответствующий значок (обведен красной рамкой на <a href="#fig31">рис. 3.1</a>). Будет открыто приложение с графическим оконным интерфейсом по своему функционалу подобное проводнику в операционной системе Windows.

> [!NOTE]
> _Все дальнейшие действия по подключению Яндекс Диска к компьютеру в этой операционной системе, будут выполнены с использованием открывшегося окна приложения "**Файлы**"._

<a name="fig31"></a>

![Приложение "Файлы" Gnome Linux](https://github.com/tsf-soft/django-test-1/assets/6228605/37134f3c-df9a-4bed-8141-263bdd89870a)
_<p>Рисунок 3.1. Приложение "Файлы" GNOME Linux</p>_

</br>

### 3.2. Установка параметров сетевого подключения

<a name="chapt_32"></a>

На левой "**Панели расположений**" приложения "**Файлы**", внизу (<a href="#fig32">рис. 3.2</a>), нужно выбрать  пункт "**+ Другие места**".

<a name="fig32"></a>

![Доступные метоположения файлов на компьютере](https://github.com/tsf-soft/django-test-1/assets/6228605/5bdd7aca-063b-49bf-b6cf-4e21c27b9bbd)
_<p>Рисунок 3.2. Доступные местоположения файлов на компьютере</p>_

</br>

### 3.3. Подключение к сервису Яндекс Диска

<a name="chapt_33"></a>

В поле "**Подключится к серверу**" (<a href="#fig33">рис. 3.3</a>) приложения "**Файлы**", нужно ввести адрес сервера в формате:

```bash

davs://Имя_вашего_аккаунта@webdav.yandex.ru

```

> Здесь: <br/>
> _**davs**_ - префикс протокола подключения (должен быть именно таким); <br/>
> _**Имя_вашего_аккаунта**_ - имя <a href="#acc_create">аккаунта</a> зарегистрированное вами в Яндекс ID; <br/>
> _**webdav.yandex.ru**_ - сетевое местоположения сервиса Яндекс Диска. <br/>

После ввода адреса сервера, - нажать на кнопку "**Подключиться**" (<a href="#fig33">рис. 3.3</a>).

<a name="fig33"></a>

![Элементы интерфейса, связанные с подключением](https://github.com/tsf-soft/django-test-1/assets/6228605/5aced32d-037b-4595-aa00-bd320a453d60)
_<p>Рисунок 3.3. Элементы интерфейса, связанные с подключением</p>_

</br>

В открывшейся форме "**Требуется аутентификация**" (Authentication Required) ввести установленный ранее <a href="#fig13">индивидуальный пароль приложения</a>, после чего нажать кнопку "**Разблокировать**" (<a href="#fig34">рис 3.4</a>). Установка чекбокса "**Запомнить пароль**" позволяет автоматически заполнять поле пароля при последующих подключениях к сетевому расположению. Значение чекбокса оп умолчанию `false` (не установлен).

<a name="fig34"></a>

![Форма аутентификации](https://github.com/tsf-soft/django-test-1/assets/6228605/ed1e92da-1c93-496c-8f5e-c4df8c6b7c26)
_<p>Рисунок 3.4. Форма аутентификации</p>_

</br>

### 3.4. Оценка полученного результата

<a name="chapt_34"></a>

На <a href="#fig35">рис. 3.5</a> показано приложение "**Файлы**" с открытым содержимым сетевого расположения (сетевого диска/сетевой папки), - которое является подключенным к компьютеру Яндекс Диском. Как видно из рисунка открытое сетевое расположение содержит все те-же файлы, которые были доступны при подключении Яндекс Диска к персональному компьютеру с <a href="#fig26">OS Windows</a>.

<a name="fig35"></a>

![Содержимое подключенного сетевого диска](https://github.com/tsf-soft/django-test-1/assets/6228605/19defb1f-7d8a-4305-b481-30766dec6950)
_<p>Рисунок 3.5. Содержимое подключенного сетевого диска</p>_

</br>

Дополнительно, можно изменить "длинный" идентификатор сетевого расположения (рис. 3.5) на более короткий, например напоминающий идентификатор диска в операционной системе Windows, путём создания ссылки-закладки.

Для этого в приложении "**Файлы**" нужно:
- на подключённом сетевом расположении вызвать контекстное меню правой кнопкой мыши;
- в открывшемся контекстном меню выбрать пункт "**Добавить в закладки**";
- перейти вниз панели "**Расположения**", найти добавленную только-что закладку и вызвать контекстное меню правой кнопкой мыши (<a href="#fig35">рис. 3.6</a>);
- в открывшемся контекстном меню выбрать пункт "**Переименовать...**";
- в появившейся форме "**Имя**", - ввести желаемое короткое имя, например "**Y**".

<a name="fig36"></a>

![Переименование закладки](https://github.com/tsf-soft/django-test-1/assets/6228605/fdaad1f6-be48-4ff3-a8bc-189c08fcb047)
_<p>Рисунок 3.6. Контекстное меню переименования закладки</p>_

<br/>

Результат последовательности действий по добавлению короткой ссылки на подключенный Яндекс Диск показан на <a href="#fig35">рис. 3.7</a>.

<a name="fig37"></a>

![Короткое имя подключенного сетевого диска](https://github.com/tsf-soft/django-test-1/assets/6228605/8e85eaa1-1db0-4f3d-9efd-be6e1ce8323b)
_<p>Рисунок 3.7. Короткое имя подключенного сетевого диска</p>_

<br/>

<a name="con_linux_cli"></a>

## 4. Подключение Яндекс Диска в OS Linux Ubuntu (CLI)

Здесь аббревиатура [CLI](https://ru.wikipedia.org/wiki/Интерфейс_командной_строки) (Command line interface) - означает использование приложения командного интерпретатора в котором все выполняемые команды вводятся в виде строки текста. Результат выполнения команд командным интерпретатором также выводится в виде текстровых строк в терминал интерпретатора.

Существует несколько наиболее популярных интерпретаторов командной строки, при этом в каждой операционной системе как правило свой набор приложений - командных интерпретаторов. В Linux наиболее используемым являетя интерпретатор [Bash](https://ru.wikipedia.org/wiki/Bash), в Windows это [PowerShell](https://ru.wikipedia.org/wiki/PowerShell), в macOS - [Zsh](https://ru.wikipedia.org/wiki/Zsh), при этом версии командного интерпретатора **Bash**, реализованы для всех операционных системах.

В этом разделе руководства будет продемонстрировано подключение Яндекс Диска в качестве сетевого диска к компьютеру с операционной системе Linux Ubuntu без графической оболочки (серверный вариант) используя командный интерпретатор **Bash**. Работа будет проведена путём подключения к Linux-машине по [SSH](https://ru.wikipedia.org/wiki/SSH). Последовательность шагов для достижения указанной цели следующая:
- <a href="#chapt_41">подключиться к Linux-машине используя CLI-интерфейс</a>;
- <a href="#chapt_42">выполнить консольные команды подключения Яндекс Диска</a>;
- <a href="#chapt_43">выполнить настройку подключаемого аккаунта</a>;
- <a href="#chapt_44">оценить полученный результат</a>.

Далее подробно о каждом шаге.

### 4.1. Подключение к Linux-машине

<a name="chapt_41"></a>

Для подключения к Linux-машине, на удалённом компьютере нужно запустить терминал **Bash**. После чего войти в Linux Ubuntu с аккаунтом зарегистрированного в системе пользователя. На <a href="#fig41">рис. 4.1</a> показано окно терминала **Bash**, подключенного к Linux-машине. На рисунке показано, что интерпретатор ожидает ввода команд.

> [!NOTE]
> _**Примечание:**
> Демонстрируемый здесь командный интерпретатор является составной частью утилиты MobaXterm, которая в т.ч. реализована в OS Windows. Для достижения этого же результата можно воспользоваться другим командным интерпретатором, либо воспользоваться собственной консолью OS Linux Ubuntu, если к ней имеется доступ._

<a name="fig41"></a>

![Терминал Bash](https://github.com/tsf-soft/django-test-1/assets/6228605/206da15d-889a-4ad8-a611-18781bf1e8ec)
_<p>Рисунок 4.1. Консольный клиент, подключенный к Linux-машине</p>_

</br>

### 4.2. Подключение Яндекс Диска с использованием консольных команд

<a name="chapt_42"></a>

Прежде всего нужно перейти в режим превилегированного пользователя с полномочиями суперпользователя (**root**). Для этого нужно ввести в терминале команду `sudo su` (строка 1 <a href="#lst41">лист. 4.1</a>). Командный интерпретатор затребует пароль пользователя под которым вы вошли в систему (строка 2 <a href="#lst41">лист. 4.1</a>). Здесь нужно ввести пароль пользователя помня при этом, что в Unix-системах, разновидностью которых является Linux Ubuntu, - при вводе пароля в окне терминала ничего не отображается (символы-заполнители также не отображаются).

<a name="lst41"></a>

```bash

1 tsf@linux-tsf:~$ sudo su
2 [sudo] password for tsf:
3 root@linux-tsf:/home/tsf#

```
_<p>Листинг 4.1. Переход в режим суперпользователя Linux</p>_

> [!NOTE]
> _**Примечание:**
> В лист. 4.1 введена только одна команда `sudo su`, все прочие символы, являются символами-приглашениями операционной системы._
> _Сюда относятся:</br>_
> - _промпт `tsf@linux-tsf:~$` идентифицирующий обычного пользователя системы Linux находящегося в домашнем каталоге;</br>_
> - _промпт `[sudo] password for tsf:` предлагающий ввести пароль текущего пользователя для перехода в режим суперпользователя;</br>_
> - _промпт `root@linux-tsf:/home/tsf#` показывающий, что активный пользователь (tsf) находится в домашнем каталоге `/home/tsf`, на компьютере с именем: `linux-tsf:` и имеет полномочия администратора (`root`)._

Далее нужно получить открытый ключ шифрования `YANDEX-DISK-KEY.GPG` из репозитария Яндекс Диска, после чего добавить полученный ключ в список надёжных репозитариев. Эти две консольные команды показаны в <a href="#lst42">лист.4.2</a>.

<a name="lst42"></a>

```bash

1 wget -O YANDEX-DISK-KEY.GPG http://repo.yandex.ru/yandex-disk/YANDEX-DISK-KEY.GPG
2 apt-key add YANDEX-DISK-KEY.GPG

```
_<p>Листинг 4.2. Работа с открытым ключем шифрования</p>_

> [!NOTE]
> _**Примечание:**_
> _Команда `apt-key` в настоящее время устарела, поскольку её действие носит глобальный характер, что может сказаться на безопасности, однако её использование не запрещено. Ожидается, что в будующем эта команда будет полностью заменена._

Следующим действием нужно выполнить создание списка `sourse.list.d` и обновить список доступных пакетов во всех зарегистрированных в системе репозиториях. Это осуществляется командами, показанными в <a href="#lst43">лист. 4.3</a>.

<a name="lst43"></a>

```bash

1 echo "deb http://repo.yandex.ru/yandex-disk/deb/ stable main" >> /etc/apt/sources.list.d/yandex-disk.list
2 apt update

```
_<p>Листинг 4.3. Обновление списка пакетов, доступных в зарегистрированных репозиториях</p>_

Теперь всё готово для установки консольного клиента Яндекс Диска. Установка выполняется одной командой менеджера зависимостей операционной системы `apt` (advanced packaging tool). Команда установки показана в строке 1 <a href="#lst44">лист. 4.4</a>, после чего можно выйти из режима суперпользователя (строка 2 <a href="#lst44">лист.4.4</a>) выполнив команду `exit`.

<a name="lst44"></a>

```bash

1 apt install yandex-disk
2 exit

```
_<p>Листинг 4.4. Установка консольного клиента Яндекс Диска</p>_

</br>

### 4.3. Настройка подключаемого аккаунта

<a name="chapt_43"></a>

Выполнение настройки параметров подключаемого Яндекс Диска производим командой <a href="#lst45">лист. 4.5</a>. При этом для авторизации в процессе выполнения настройки необходимо воспользоваться веб-браузером на любом доступном устройстве подключенном к сети интернет (<a href="#fig43">рис. 4.3</a>).

<a name="lst45"></a>

```bash

yandex-disk setup

```
_<p>Листинг 4.5. Запуск настройки подключаемого Яндекс Диска</p>_

Команда `yandex-disk setup` запустит утилиту настройки (<a href="#fig42">рис. 4.2</a>). Утилита поставит перед пользователем ряд интерактивных вопросов. Если в ответ на эти вопросы ничего не вводить, то будут приняты значения по умолчанию. Вопросы утилиты настройки такие:
- Использовать прокси-сервер [y/N]? (значение по умолчанию НЕТ);
- Выполнить авторизацию в браузере по адресу: `https://ya.ru/device` с нужным аккаунтом и предложенным кодом (<a href="#fig43">рис. 4.3</a>) в течении ограниченного временного интервала;
- Ввести путь к папке Яндекс Диска, т.е. выбрать не только местоположение папки с Яндекс Диском, но и задать название этой папки (по умолчанию папка имеет название  `Yandex.Disk` и будет находится в домашнем каталоге текущего пользователя);
- Запускать Яндекс.Диск при входе в систему? (значение по умолчанию ДА).

На <a href="#fig42">рис. 4.2</a> видно, что для подключаемого Яндекс Диска задано короткое имя **Y1**, все остальные параметры оставлены по умолчанию. 

<a name="fig42"></a>

![Настройки консольного клиента в системе](https://github.com/tsf-soft/django-test-1/assets/6228605/e2fe4dae-9bd1-4685-8e5c-bc35b8cbfe2d)
_<p>Рисунок 4.2. Настройка консольного клиента в системе</p>_

</br>

<a name="fig43"></a>

![Форма авторизации в браузере](https://github.com/tsf-soft/django-test-1/assets/6228605/8d96aeeb-36dc-4725-8b89-2dbf62291e56)
_<p>Рисунок 4.3. Форма авторизации в браузере</p>_

</br>

При успешной авторизации в процессе настройки с помощью браузера, - будет отображена форма <a href="#fig44">рис. 4.4</a> уведомляющая об успешно пройденной авторизации.

<a name="fig44"></a>

![Успешно пройденная авторизация](https://github.com/tsf-soft/django-test-1/assets/6228605/7ec5fb02-d711-423f-9ede-ac6d97731cc1)
_<p>Рисунок 4.4. Успешно пройденная авторизация</p>_

> [!NOTE]
> _**Примечание:**_
> _Авторизация в браузере будет произведена в текущем активном аккаунте Яндекс ID пользователя. Иначе говоря вы подключите тот экземпляр Яндекс Диска, который привязан к вашему текущему активному аккаунту. Если вам нужен другой экземпляр Яндекс Диска, то измените текущий активнй аккаунт путём авторизации в нужном аккаунте, после чего выполняйте авторизацию._

</br>

### 4.4. Оценка полученного результата

<a name="chapt_44"></a>

Просмотр содержимого подключенного сетевого диска с помощью консольной команды `ls` <a href="#lst46">лист. 4.6</a>, - показан на <a href="#fig42">рис. 4.2</a>.

<a name="lst46"></a>

```bash

ls -la Y1/

```
_<p>Листинг 4.6. Просмотр содержимого подключенного Яндекс Диска</p>_

На <a href="#fig42">рис. 4.2</a> видно, что содержимое подключенного сетевого диска такое-же, что и содержимое этого же диска, подключенного для варианта <a href="#fig26">OS Windows</a> и для варианта  <a href="#fig35">OS Linux Ubuntu GUI</a>.

Следует отметить, что консольный клиент позволяет подключить много экземпляров Яндекс Диска и одновременно использовать их. Каждый из подключенных экземпляров может как принадлежать различным зарегистрированным <a href="#acc_create">аккаунтам Яндекс ID</a>, так и работать как повторное подключение ранее уже подключенного аккаунта.

На <a href="#fig45">рис. 4.5</a> показан вариант, в котором подключено 4 экземпляра Яндекс Диска. Эти экземпляры представлены следующими каталогами: Y1, Y2, Yandex.Disk, YY. Для каталога Yandex.Disk дополнительно создана короткая символьная ссылка YD командой:

<a name="lst47"></a>

```bash

ln -s ./Yandex.Disk ./YD

```
_<p>Листинг 4.7. Создание символьной ссылки на каталог Yandex.Disk</p>_

</br>

<a name="fig45"></a>

![Несколько подключенных аккаунтов Яндекс Диска](https://github.com/tsf-soft/django-test-1/assets/6228605/ddd675d6-6b8e-4161-99ef-26b1af54aacc)
_<p>Рисунок 4.5. Несколько подключенных аккаунтов Яндекс Диска</p>_

</br>

Поскольку в Unix-подобных операционных системах "всё-есть-файл", т.е. устройства считаются "плоскими" файлами (каталогами), то подключенный в этом разделе руководства каталог Яндекс Диска по сути, является полноценным сетевым диском.


