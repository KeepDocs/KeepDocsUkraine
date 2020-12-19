# Виправлення проблем

У цьому розділі показано, як боротися з деякими поширеними помилками і попередженнями, а також як їх усувати.

** Зміст розділу **
- [Introduction and Log Access (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Troubleshooting#introduction-and-log-access)
- [Common Errors and Warnings (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Troubleshooting#common-errors-and-warnings)
    - [Just ignore these WARNINGS (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Troubleshooting#just-ignore-these-warnings)
    - [Config.toml File errors (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Troubleshooting#configtoml-file-errors)
    - [Errors after updating addresses inside Config.toml (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Troubleshooting#errors-after-updating-addresses-inside-configtoml)
    - [Errors from Token Delegation / Contracts authorization (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Troubleshooting#errors-from-token-delegation--contracts-authorization)
- [Other Warnings (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Troubleshooting#other-warnings)

## Введення і доступ до логів
** Перш за все: переконайтеся, що ви використовуєте останні версії клієнтів з останніми контрактами. Підключивши однорангові Ноди + запити infura. **

Ви можете перевірити логи для кожної ноди за допомогою цієї команди: `docker logs * node-name *`
Ви можете визначити ім'я Ноди командою `docker ps` (last column -> names)
Ви також можете побачити деякі інші поширені способи отримання конкретної інформації з логів за допомогою [цих команд] (https://github.com/Estebank97/Keep-Node-Operation/wiki/Manage-your-Nodes#ecdsa-node-maintenance)

Якщо ви бачите підключення бенкети - все ок:

<P align = "center">
  <Img width = "719" alt = "Intro" src = "https://user-images.githubusercontent.com/68087535/89208516-e7419d80-d592-11ea-9822-13be0ae02cb1.png">
</ P>

У цьому прикладі [27] підключених бенкетів.


## Загальні помилки і попередження
Якщо ви бачите підключення бенкети - ваша нода працює.

З іншого боку, якщо ви бачите CRITICAL або WARNING, можливо, ваша нода не працює належним чином.
Давайте подивимося на кілька поширених прикладів і вкажемо спосіб їх вирішення:

### Просто ігноруйте ці WARNINGS

<P align = "center">
  <Img width = "719" alt = "Ignore" src = "https://user-images.githubusercontent.com/68087535/89208525-ec9ee800-d592-11ea-8836-ac5276be14b9.png">
</ P>
Не вдається підключитися з якимось конкретним бенкетом, це не повинно бути проблемою ... Як бачите, ви підключили 71 бенкет, так що все в порядку!

### Config.toml помилка файлу
Перевірте ваш config.toml можливо там є граматичні помилки:
<P align = "center">
  <Img width = "719" alt = "config" src = "https://user-images.githubusercontent.com/68087535/89208529-ee68ab80-d592-11ea-944e-c6538db35110.png">
</ P>


Переконайтеся, що ви правильно встановили пароль, в `export KEEP_CLIENT_ETHEREUM_PASSWORD =" your_eth_wallet_password "`:
<P align = "center">
  <Img width = "719" alt = "pass1" src = "https://user-images.githubusercontent.com/68087535/89208536-f1fc3280-d592-11ea-9977-0d9bb22dfc9a.png">
</ P>



Тут показані контракти, які визначені в файлі Config.toml. Переконайтеся, що у вас є останні оновлення. (Ви можете двічі перевірити закріплені повідомлення в каналі Discord або в Github (https://github.com/keep-network/keep-ecdsa/blob/master/docs/run-keep-ecdsa.adoc):

<P align = "center">
  <Img width = "719" alt = "contract1" src = "https://user-images.githubusercontent.com/68087535/89208553-f4f72300-d592-11ea-8784-0e055f75ed6b.png">
</ P>

### Помилки після поновлення адрес всередині Config.toml
Час від часу необхідно виконувати деякі оновлення Ноди, наприклад коли Keep Team оновлює адреси контрактів:
<P align = "center">
  <Img width = "750" alt = "contract2" src = "https://user-images.githubusercontent.com/68087535/89208558-f6285000-d592-11ea-942b-a22477b3b5f1.png">
</ P>
In this example the addresses where changed at the wrong spot inside Config.toml.


### Помилки з Token Delegation / Contracts authorization
<P align = "center">
  <Img width = "719" alt = "Autho" src = "https://user-images.githubusercontent.com/68087535/89208564-f7597d00-d592-11ea-8c88-ec94438bb1d5.png">
</ P>
Вам потрібно перейти в Keep Token app і перевірити, відсутня чи делегування токена або авторизація контрактів.


## Інші попередження
<P align = "center">
  <Img width = "719" alt = "Other 1" src = "https://user-images.githubusercontent.com/68087535/89208567-f7f21380-d592-11ea-9c87-71cd7227bf5f.png">
</ P>
Якась проблема зі зберіганням контрактів в мережі Keep, з цим нічого не поробиш.

<P align = "center">
  <Img width = "719" alt = "Other 2" src = "https://user-images.githubusercontent.com/68087535/89208572-f9bbd700-d592-11ea-86ed-409db54acde8.png">
</ P>
Проблема в ланцюжку, як-то пов'язана зі спробою приєднатися до об'єднаного пулу жеребкування.
    
    !> @ Nico186 зробив відмінний [документ] (https://docs.google.com/document/u/2/d/e/2PACX-1vRYtVyLSwuNBL9Xk-M1HeHloJ7MIGqwiEzsuXYnKHQqnSz2gfd2Q3czJeOzEferPKIr7GvIznQxsckb/pub) з інтерпретацією логів помилок і попереджень KEEP.

---
`Джерело з офіційної документації Keep Team, відредагований і доповнений спільнотою. '[Джерело] (https://keep-network.gitbook.io/staking-documentation/) `

`Автори: Ramaruro, EstebanK`
`Переклад: ingag`
