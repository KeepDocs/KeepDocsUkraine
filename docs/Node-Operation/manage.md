# Управління нодамі
В цьому розділі розглядаються питання управління нодамі: після настройки і запуску, ви повинні контролювати їх роботу і оновлювати їх всякий раз, коли команда Keep запускає нові контракти або нові версії клієнтів.

## Кращі рекомендації


### Окремі INFURA акаунти

Створіть один проект INFURA для кожної еоди, щоб бачити окремі дії для кожного проекту.
Це швидкий і простий спосіб перевірити, чи активовано нод, але це не повинно бути основним способом перевірки.
<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/88484551-07d77b00-cf35-11ea-974e-5dddd0162bab.png">
</ P>


### Використовуйте різні Virtual Private Server (VPS) для нод

Хоча це збільшує вартість експлуатації, якщо виникають проблеми з операціями або оновленнями, ви можете грамотніше розподілити ризики.

<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/88492899-be5a5080-cf73-11ea-972d-715dca658e0c.png">
</ P>

## Перевірка працездатності Ноди

!> ** @ Herobrine ** зробив приголомшливе додаток, яке ви можете запустити, щоб перевірити працездатність Ноди: [KeepNode.app] (https://keepnode.app/)

### Обслуговування ECDSA Ноди

Основна перевірка, яку ви повинні зробити, це переконатися, що нода ECDSA підключена до бенкетів:

Використовуйте термінал: `sudo docker logs ecdsa --since 5m | grep "connected" `

<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/88097681-2668fb00-cb5e-11ea-94d4-c080e20d5a15.png">
</ P>

Ви також можете перевірити Keep Creation.

Використовуйте термінал: `sudo docker logs ecdsa 2> & 1 | grep "new keep" `

<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/88484709-30ac4000-cf36-11ea-8baf-3a54b48523b2.png">
</ P>

Подивитися лог "підключених" бенкетів

Використовуйте термінал: `sudo docker logs ecdsa --since 5m | grep "connected" `

<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/88487822-226a1e00-cf4e-11ea-8351-60cf0a68d968.png">
</ P>


!> Якщо запущені Ноди в основній мережі, обов'язково виконайте кроки - [Mainnet Node Operation Section] (https://estebank97.github.io/Keep-Node-Docs/#/Node-Operation/mainnet) і використовуйте [Community Tools] (https://estebank97.github.io/Keep-Node-Docs/#/basics/tools).


## Недостатнє забезпечення та ліквідація

Існує серйозний ризик того, що через відносних коливань цін пари ETH / BTC ваше забезпечення (фактично, заставу для Keep (ів), який ви підписали) виявиться недостатнім, і ви піддастеся ризику ліквідації.
Процес докладно описаний в [tBTC System Design Document] (https://docs.keep.network/tbtc/index.pdf), сторінки 19-20

Стаття від Bison Trail, [Keep Active Management] (https://bisontrails.co/keep-active-participation/), пояснює цей процес ліквідації і перераховує кілька заходів, які можна зробити, щоб уникнути цієї проблеми.

В даний час моніторинг повинен бути ручним, тобто перевірка відносних коливань цін ETH / BTC і додавання застави ETH.

[Latenthero] (https://discord.com/channels/590951101600235531/590951101600235533/737707953221664779) створив [Telegram Bot] (https://t.me/keep_alert_bot) для попередження, коли доступний ETH нижче встановленого користувачем порогу. Код для бота можна побачити і в кінцевому підсумку перепрофілювати [тут] (https://github.com/latenthero/keep-alert-bot). Він доступний для Testnet з серпня 2020 року.

Цей документ від Experience # 2376 надає більш детальну інформацію з посиланнями на задіяний програмний код: [tBTC risk - liquidation and slashing details] (https://hackmd.io/OzIeyWcfTVO69zIF67XCkg). Цей графік з документа добре пояснює ризики.
<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/88967178-0975ab80-d273-11ea-9696-15f2ce8995c5.png">
</ P>

h / t ssh


## Оновлення нод
Час від часу команда розробників Keep буде випускати нові образи Docker для обох нод і оновлювати відповідні контракти Ethereum.

### Основні витяги з гайда по оновлень

Час від часу команда розробників Keep буде випускати нові образи Docker для обох нод і оновлювати відповідні контракти Ethereum. Дивіться цей [Run ECDSA Keep] (https://github.com/keep-network/keep-ecdsa/blob/master/docs/run-keep-ecdsa.adoc#83-authorizations) документ.
Вам необхідно зробити наступне:
* Зупиніть ноду -> `sudo docker stop ecdsa`
* Відредагуйте файл "config.toml" -> `nano $ HOME / keep-ecdsa / config / config.toml`
* Оновлення контракти і списки партнерів, як зазначено командою Keep
  - Наприклад, це оновлення контрактів і списку бенкетів було зроблено в червні 2020 роки (виділено зеленим кольором).

<P align = "center">
  <Img width = "900" src = "https://user-images.githubusercontent.com/68167410/88488480-0026cf00-cf53-11ea-9ef6-cf65551f5cb1.png">
</ P>
  
  Як альернатіву можна використовувати гайд - ** Papyasha ** [Update Nodes] (https://gist.github.com/papyasha/7d97cb53aa1153cc65b0535c2b9f23e3) показує чистий спосіб оновлення файлів конфігурації шляхом їх видалення і повторного запуску. Він також включає посилання на вихідний запуск нод з усіма необхідними деталями.

---
### Оновлення 2 вересня 2020 року (+ 8 вересня)
Ключові дії з оновлення обох нод наступні:
* Отримайте новий грант KEEP Tokens для Testnet Faucet:
  - https://us-central1-keep-test-f3e0.cloudfunctions.net/keep-faucet-ropsten?account= ** `" Your Operator Ethereum Address "` **
* Стейкніте грант в [KEEP Dapp] (https://dashboard.test.keep.network/tokens/overview) (this address for Testnet)
* Авторизуйтесь контракти KEEP Dapp
  - Авторизуйтесь [Random Beacon] (https://dashboard.test.keep.network/applications/random-beacon)
  - Авторизуйтесь [ECDSA] (https://dashboard.test.keep.network/applications/tbtc) and add ETH for Bonding
* Зупинка Docker Containers:
  - Переконайтеся що вказали коректні імена - `sudo docker ps`.
  - для Random Beacon: `sudo docker stop keep-client`
  - для ECDSA: `sudo docker stop ecdsa`
* Видаліть Current Containers:
  - для Random Beacon: `sudo docker rm keep-client`
  - для ECDSA: `sudo docker rm ecdsa`
* Завантажте New Docker Images:
  - для Random Beacon: `sudo docker pull keepnetwork / keep-client: v1.3.0-rc.4`
  - для ECDSA: `sudo docker pull keepnetwork / keep-ecdsa-client: v1.2.0-rc.5`
* Оновлення Config.toml:
  - Якщо обидві Ноди працюють на одному VPS, пам'ятайте, що кожен файл конфігурації перебуває в окремій папці. У цьому прикладі названі keep-client і keep-ecdsa.
  - Переконайтеся що вказали коректні імена папок `ls`.
  - для Random Beacon: `nano $ HOME / keep-client / config / config.toml`
     - KeepRandomBeaconOperator = `" 0xC8337a94a50d16191513dEF4D1e61A6886BF410f "`
     - TokenStaking = `" 0x234d2182B29c6a64ce3ab6940037b5C8FdAB608e "`
     - KeepRandomBeaconService = `" 0x6c04499B595efdc28CdbEd3f9ed2E83d7dCCC717 "`
  - для ECDSA: `nano $ HOME / keep-ecdsa / config / config.toml`
     - BondedECDSAKeepFactory = `" 0x9EcCf03dFBDa6A5E50d7aBA14e0c60c2F6c575E6 "`
     - Sanctioned Applications = `" 0xc3f96306eDabACEa249D2D22Ec65697f38c6Da69 "`
* Запустіть Docker Containers:
- Запишіть це як одну команду і пам'ятайте, що вона може змінитися відповідно до керівництвом, яке ви використовували спочатку (наприклад, порти можуть відрізнятися від 3919: 3919).
  - Переконайтеся, що ви посилаєтеся на нові образи Docker і запускаєте кожен у своїй папці (якщо на тому ж VPS)!
  
  
  - для Random Beacon:
  
  
        sudo docker run -dit
        --restart always
        --volume $ HOME / keep-client: / mnt
        --env KEEP_ETHEREUM_PASSWORD = $ KEEP_CLIENT_ETHEREUM_PASSWORD
        --env LOG_LEVEL = debug
        --log-opt max-size = 100m
        --log-opt max-file = 3
        --name keep-client
        -p 3919: 3919
        keepnetwork / keep-client: v1.3.0-rc.4 --config /mnt/config/config.toml start
      
      
  - для ECDSA:
  
  
        sudo docker run -d
        --restart always
        --entrypoint / usr / local / bin / keep-ecdsa
        --volume $ HOME / keep-ecdsa: / mnt / keep-ecdsa
        --env KEEP_ETHEREUM_PASSWORD = $ KEEP_CLIENT_ETHEREUM_PASSWORD
        --env LOG_LEVEL = debug
        --log-opt max-size = 100m
        --log-opt max-file = 3
        --name ecdsa
        -p 3919: 3919
        keepnetwork / keep-ecdsa-client: v1.2.0-rc.5 --config /mnt/keep-ecdsa/config/config.toml start

* Перевірте логи на підключення бенкетів:
  - для Random Beacon: `sudo docker logs keep-client 2> & 1 --since 5m | grep "number of connected peers" `
  - для ECDSA: `sudo docker logs ecdsa 2> & 1 --since 5m | grep "number of connected peers" `
  - Якщо він показує якісь помилки, спочатку переконайтеся, що контракти авторизовані в дашборда. Іноді потрібно повторити все знову.

* Нарешті, не забудьте додати тестовий ETH до прив'язки tBTC в дашборда!

---
### Август 7, 2020 Оновлення
Ключові дії з оновлення обох нод наступні:
* Отримайте новий грат KEEP Tokens для Testnet Faucet:
  - https://us-central1-keep-test-f3e0.cloudfunctions.net/keep-faucet-ropsten?account= ** `" Your Operator Ethereum Address "` **
* Застейкайте його в [KEEP Dapp] (https://dashboard.test.keep.network/tokens/overview) (this address for Testnet)
* Авторизуйтесь контракти в KEEP Dapp
  - Авторизуйтесь [Random Beacon] (https://dashboard.test.keep.network/applications/random-beacon)
  - Авторизуйтесь [ECDSA] (https://dashboard.test.keep.network/applications/tbtc) and add ETH for Bonding
* Зупиніть Docker Containers:
  - Переконайтеся що вказали коректні імена - `sudo docker ps`.
  - для Random Beacon: `sudo docker stop keep-client`
  - для ECDSA: `sudo docker stop ecdsa`
* Видаліть Current Containers:
  - для Random Beacon: `sudo docker rm keep-client`
  - для ECDSA: `sudo docker rm ecdsa`
* Завантажте New Docker Images:
  - для Random Beacon: `sudo docker pull keepnetwork / keep-client: v1.3.0-rc`
  - для ECDSA: `sudo docker pull keepnetwork / keep-ecdsa-client: v1.2.0-rc`
* Оновлення Config.toml:
  - Якщо обидві Ноди працюють на одному VPS, пам'ятайте, що кожен файл конфігурації перебуває в окремій папці. У цьому прикладі названі keep-client і keep-ecdsa.
  - Переконайтеся що вказали коректні імена папок `ls`.
  - для Random Beacon: `nano $ HOME / keep-client / config / config.toml`
     - KeepRandomBeaconOperator = `" 0xf417b31104631280adF9F6828ee19985BC299fdC "`
     - TokenStaking = `" 0x8117632eC1D514550b3880Bc68F9AC1A76c9C67B "`
     - KeepRandomBeaconService = `" 0xd83248e311DC2Ba0d2A051e86f0678d8857f6ADD` "
  - для ECDSA: `nano $ HOME / keep-ecdsa / config / config.toml`
     - BondedECDSAKeepFactory = `" 0xb37c8696cD023c11357B37b5b12A9884c9C83784 "`
     - Sanctioned Applications = `" 0x9F3B3bCED0AFfe862D436CB8FF462a454040Af80 "`
* Запустіть Docker Containers:
  - Запишіть це як одну команду і пам'ятайте, що вона може змінитися відповідно до керівництвом, яке ви використовували спочатку (наприклад, порти можуть відрізнятися від 3919: 3919).
  
  - для Random Beacon: `sudo docker run -dit --restart always --volume $ HOME / keep-client: / mnt --env KEEP_ETHEREUM_PASSWORD = $ KEEP_CLIENT_ETHEREUM_PASSWORD --env LOG_LEVEL = debug --log-opt max-size = 100m --log-opt max-file = 3 --name keep-client -p 3919: 3919 keepnetwork / keep-client: v1.3.0-rc --config /mnt/config/config.toml start`
  - для ECDSA: `sudo docker run -d --restart always --entrypoint / usr / local / bin / keep-ecdsa --volume $ HOME / keep-ecdsa: / mnt / keep-ecdsa --env KEEP_ETHEREUM_PASSWORD = $ KEEP_CLIENT_ETHEREUM_PASSWORD --env LOG_LEVEL = debug --log-opt max-size = 100m --log-opt max-file = 3 --name ecdsa -p 3919: 3919 keepnetwork / keep-ecdsa-client: v1.2.0-rc - config /mnt/keep-ecdsa/config/config.toml start`

* Перевірте логи на підключення бенкетів:
  - для Random Beacon: `sudo docker logs keep-client 2> & 1 --since 5m | grep "number of connected peers" `
  - для ECDSA: `sudo docker logs ecdsa 2> & 1 --since 5m | grep "number of connected peers" `
  - Якщо він показує якісь помилки, спочатку переконайтеся, що контракти авторизовані в дашборда. Іноді потрібно повторити все знову.

* Нарешті, не забудьте додати тестовий ETH до прив'язки tBTC в дашборда!

---
`Джерело з офіційної документації Keep Team, відредагований і доповнений спільнотою. '[Джерело] (https://keep-network.gitbook.io/staking-documentation/) `

`Автори: Ramaruro, EstebanK`
`Переклад: ingag`
