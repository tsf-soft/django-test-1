# Подключение Яндекс Диска в качестве сетевого диска компьютера

<br/>

## О чём пойдёт речь

Яндекс Диск - это облачный сервис, позволяющий хранить файлы в облачной инфрастуктуре поддерживаемой компанией Яндекс.
Используя этот сервис вы сможете работать с файлами размещаемыми на таком диске - с любого устройства подключенного к сети интернет.
Подробнее о возможностях предоставляемых сервисом можно узнать [здесь](https://360.yandex.ru/disk/).

Для большего удобства в работе с сервисом, Яндекс Диск может быть подключен к персональному компьютеру как обычный сетевой диск компьютера.
Подключив Яндекс Диск к своему компьютеру таким образом, - вы сможете средствами операционной системы выполнять с ним те же действия что и с любым другим дисковым накопителем, имеющимся в вашем компьютере.

Превратить облачный сервис в обычный диск, позволяет протокол [WebDAV](https://ru.wikipedia.org/wiki/WebDAV).

<br/>

## Прежде чем начать

<a name="acc_create"></a>

Для того, чтобы начать пользоваться сервисом Яндекс Диск нужно быть зарегистрированным в Яндекс через аккаунт **Яндекс ID**.
Если вы ещё не зарегистрированы в Яндекс, то вам нужно зарегистрировать аккаунт **Яндекс ID**. Подробнее о том, как это сделать сказано [здесь](https://yandex.ru/support/id/authorization/registration.html).
Вопросы безопасности связанные с регистируемым аккаунтом касающиеся требований к паролям, в том числе для доступа к Яндекс Диску, подробно описаны в [этой статье](https://yandex.ru/support/id/authorization/app-passwords.html).

Дополнительно акцентирую ваше внимание на факторе безопасности касающимся возможности использования сервиса Яндекс Диск сторонним программным обеспечением (ПО). Сторонним ПО в данном случае является протокол [WebDEV](https://ru.wikipedia.org/wiki/WebDAV). Вам не удастся подключить Яндекс Диск в качестве сетевого диска из-за проблем с доступом (<a href="#fig1">рис. 1</a>), если вы не установите индивидуальный пароль для приложения Яндекс Диск.

![Не возможно подключиться](https://github.com/tsf-soft/django-test-1/assets/6228605/3de343fe-8cb3-4661-9278-6f49e10ec005)
_<p>Рисунок 1. Отсутствие доступа при не установленном индивидуальном пароле для приложения</p>_

<a name="fig1"></a>

<br/>

Для установки индивидуального пароля на приложение Яндекс Диск, в Яндекс ID вам нужно последовательно выбрать следующие пункты меню: _"Управление аккаунтом" --> "Безопасность" --> "Пароли приложений" --> "Файлы (WebDAV)"_ (<a href="#fig2">рис.2</a>).

![Место установки индивидуального пароля](https://github.com/tsf-soft/django-test-1/assets/6228605/d0a9a10e-53da-4974-b810-996d1b0006f2)
_<p>Рисунок 2. Последовательность элементов меню в Яндекс ID</p>_

<a name="fig2"></a>

<br/>

Нажав на последний элемент меню (п.3 на рис. 2) вы получите форму с предложением придумать новый пароль для приложения. Эта форма состоит из двух вкладок. На первой вкладке (<a href="#fig3">рис. 3</a>) вам будет предложено придумать имя для пароля. Сам пароль вы получите на второй вкладке (<a href="#fig4">рис. 4</a>) нажав на кнопку "Далее".

<a name="fig3"></a>

![Ввод имени пароля приложения](https://github.com/tsf-soft/django-test-1/assets/6228605/10a9b82e-28cc-44b4-b398-69455daf7947)
_<p>Рисунок 3. Вкладка №1 формы создания пароля приложения</p>_

<br/>

<a name="fig4"></a>

![Собственно пароль приложения](https://github.com/tsf-soft/django-test-1/assets/6228605/926cf735-583e-408d-ba46-97989118c3f2)
_<p>Рисунок 4. Вкладка №2 формы создания пароля приложения</p>_

<br/>

В случае успешного создания вами индивидуального пароля для приложения в **Яндекс ID**, - на ваш адрес электроной почты от службы поддержки Яндекс ID, придёт письмо с уведомлением о совершенном действии (<a href="#fig5">рис. 5</a>)

<a name="fig5"></a>

![Уведомление от службы поддержки](https://github.com/tsf-soft/django-test-1/assets/6228605/1d53ba70-f1c1-4379-8672-8a5a19f2b426)
_<p>Рисунок 5. Письмо-уведомление от службы поддержки Яндекс ID</p>_

<br/>

Созданный вами индивидуальный пароль для приложения храниться в Яндекс ID в зашифрованном виде. Код пароля, в т.ч. в случае вашего обращения в службу поддержки, вы можете посмотреть открыв пункт с именем созданного вами пароля (<a href="#fig6">рис. 6</a>).

<a name="fig6"></a>

![Хранение индивидуального пароля в системе](https://github.com/tsf-soft/django-test-1/assets/6228605/d0680ab8-e0c3-4394-aaa6-81ef2b78d956)
_<p>Рисунок 6. Хранение индивидуального пароля приложения в Яндекс ID</p>_

<br/>

Теперь, имея аккаунт **Яндекс ID** с отдельно установленным паролем для приложения Яндекс Диск, можно приступить к подключению сервиса Яндекс Диск в качестве сетевого диска к персональному компьютеру.

В зависимости от используемой вами операционной системы последовательность действий по достижению этой цели будет различаться. Здесь рассмотрены варианты подключения сервиса к персональным компьютерам с операционными системами **Windows** и **Linux Ubuntu**, причём для OS Linux рассмотрены два варианта: **Linux Ubuntu GUI** и **Linux Ubuntu CLI**.

<br/>

## Подключение Яндекс Диска в OS Windows

<a name="con_windows"></a>

В операционной системе Windows нужно сделать следующее:

### 1. Воспользоваться проводником Windows

В проводнике Windows вам нужно выбрать значок `Этот компьютер`. Далее выполнить один из вариантов: либо вызвать контекстное меню (<a href="#fig7">рис. 7</a>), содержащее нужный пункт  `Подключить сетевой диск...` путём нажатия правой кнопки мыши, либо в главном меню проводника (<a href="#fig8">рис. 8</a>) выбрать на ленте инструментов элемент `Подключить сетевой диск`.

<a name="fig7"></a>

![Выбор из контекстного меню](https://github.com/tsf-soft/django-test-1/assets/6228605/1e83e011-00c9-4ad0-9055-5f187721ac7e)
_<p>Рисунок 7. Контекстное меню элемента "Мой компьютер"</p>_

<br/>

<a name="fig8"></a>

![Выбор из панели инструментов проводника](https://github.com/tsf-soft/django-test-1/assets/6228605/17ce573e-254e-477d-9de9-1510ffa22e6f)
_<p>Рисунок 8. Панель инструментов проводника для элемента "Мой компьютер"</p>_

<br/>

### 2. Ввести данные в форму "Подключение сетевого диска"

Поля открывшейся формы `Подключение сетевого диска` (<a href="#fig9">рис. 9</a>) нужно установить таким образом:

- в поле `Диск` - выбрать один из предлагаемых системой свободных символов, который будет назначен смонтированному сетевому диску;
- в поле `Папка` - установить `https://webdav.yandex.ru`;
- чекбокс `Восстанавливать подключение при входе в систему` (по умолчанию этот пункт выбран), нужен для того чтобы в дальнейшем Яндекс Диск, как сетевой диск был всегда вам доступен, даже после перезагрузки;
- чекбокс `Использовать другие учётные данные` (по умолчанию не выбран) нужен, если вы планируете часто подключаться к Яндекс Диску через различные аккаунты <a href="#acc_create">Яндекс ID</a>; выбор этого чекбокса приведёт к тому, что при каждом подключении от вас потребуется ввод учётных данных с которыми вы хотите подключиться к диску.

<a name="fig9"></a>

![Форма "Подключение сетевого диска"](https://github.com/tsf-soft/django-test-1/assets/6228605/dd612dbe-7af3-4f7d-bc36-d5ae9dff8eba)
_<p>Рисунок 9. Форма "Подключение сетевого диска"</p>_

<br/>

### 3. Ввести ваши учётные данные

Открывшаяся форма `Безопасность Windows` (<a href="#fig10">рис. 10</a>) потребует от вас ввести учётные данные:

- в поле `Имя пользователя` - нужно ввести ваш логин, который вы задали при создании <a href="#acc_create">аккаунта</a>;
- в поле `Пароль` - введите <a href="#fig3">индивидуальный пароль приложения</a>, установленный вами в аккаунте;
- чекбокс `Запомнить учетные данные` (по умолчанию не выбран) - отвечает за автоматическое последующее заполнение первых двух полей введёнными вами данными, в случае его выбора.

<a name="fig10"></a>

![Форма "Безопасность Windows"](https://github.com/tsf-soft/django-test-1/assets/6228605/d41adc37-e829-4851-8517-1c56768b070d)
_<p>Рисунок 10. Форма "Безопасность Windows"</p>_



4. 
5. 




