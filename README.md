# Подключение Яндекс Диска в качестве сетевого диска компьютера

## О чём пойдёт речь

Яндекс Диск - это облачный сервис, позволяющий хранить файлы в инфрастуктуре поддерживаемой компанией Яндекс.
Используя этот сервис вы сможете работать с файлами, размещаемыми на таком диске - с любого устройства подключенного к сети интернет.
Подробнее о возможностях предоставляемых сервисом можно узнать [здесь](https://360.yandex.ru/disk/).

Для большего удобства в работе с сервисом, Яндекс Диск может быть подключен к персональному компьютеру как обычный сетевой диск компьютера.
Подключив Яндекс Диск к своему компьютеру таким образом, - вы сможете средствами операционной системы выполнять с ним те же операции что и с любым другим дисковым накопителем,
имеющимся в вашем компьютере. Превратить облачный сервис в диск, позволяет протокол [WebDAV](https://ru.wikipedia.org/wiki/WebDAV).

## Прежде чем начать

Для того, чтобы начать пользоваться сервисом Яндекс Диск нужно быть зарегистрированным в Яндекс через аккаунт **Яндекс ID**.
Если вы ещё не зарегистрированы в Яндекс, то вам нужно зарегистрировать аккаунт **Яндекс ID**. Подробнее о том, как это сделать сказано [здесь](https://yandex.ru/support/id/authorization/registration.html).
Вопросы безопасности связанные с регистируемым аккаунтом касающиеся требований к паролям, в том числе для доступа к Яндекс Диску, подробно описаны в [этой статье](https://yandex.ru/support/id/authorization/app-passwords.html).

Имея аккаунт **Яндекс ID**, можно приступить к подключению сервиса Яндекс Диск в качестве сетевого диска к персональному компьютеру. В зависимости от используемой вами операционной системы последовательность действий по достижению этой цели будет различаться. Здесь рассмотрены подключения сервиса к компьютерам с операционными системами `Windows` и `Linux Ubuntu`.

## Подключение Яндекс Диска в OS Windows

В операционной системе Windows нужно сделать следующее:

1. Воспользоваться проводником Windows.

Выбрать в проводнике Windows значок `Этот компьютер`, далее можно либо вызвать контекстное меню содержащее нужный нам пукт `Подключить сетевой диск...` путём нажатия правой кнопки мыши (рис.1), либо в главном меню проводника (рис.2) выбрать на ленте инструментов элемент `Подключить сетевой диск`.

![из контекстного меню](https://github.com/tsf-soft/django-test-1/assets/6228605/20d4123c-e694-48ed-9343-0e6de754faee)
_<p>Рисунок 1. Контекстное меню "Мой компьютер"</p>_

![из панели инструментов проводника](https://github.com/tsf-soft/django-test-1/assets/6228605/5e77e070-2908-42b6-a83e-55dab5289b6a)
_<p>Рисунок 1. Панель инструментов "Мой компьютер"</p>_


2. Ввести данные в открывшуюся форму `Подключение сетевого диска` (рис.3):

- в поле `Диск` выбрать один из предлагаемых системой свободных символов;
- в поле `Папка` установить `https://webdav.yandex.ru`;
- если вы хотите, чтобы в дальнейшем Яндекс Диск, как сетевой диск был всегда вам доступен, даже после перезагрузки, выберите чекбокс `Восстанавливать подключение при входе в систему` (по умелчанию этот пункт выбран);
- если вы выберете чекбокс `Использовать другие учётные данные` - то при подключении Яндекс Диска у вас всегда будут запрашиваться учётные данные с которыми вы хотите подключиться к диску.

3. 
4. 
5. 




