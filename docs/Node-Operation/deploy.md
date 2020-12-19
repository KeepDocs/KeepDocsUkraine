# Запуск ваших нод

У цьому розділі зібрані керівництва і підходи, розроблені різними учасниками спільноти Keep для полегшення запуску Keep Random Beacon і Keep ECDSA.

** Вміст цього розділу **
- Установка Ноди
- Офіційні міркування Keep Network про Random Beacon ноді
- Гайд для абсолютних новачків
- Інші гайди
- ECDSA нода на Amazon
- Гайди по скриптам
- Kubernetes гайд для ECDSA Ноди
- Keep на Windows


# Устновка Ноди

Ви можете підтримувати Keep Network, брати участь і отримувати винагороди, керуючи наступними нодамі:
   * Random Beacon
   * ECDSA

Прямо зараз Keep Network і система tBTC працює в тестовій мережі Ropsten.
Є кілька дуже хороших посібників, які допоможуть вам в процесі запуску обох нод.
Головні кроки установки:
- Створіть на [Infura] (https://infura.io/) аккаунт.
- Створіть Ethereum гаманець, використовуйте "My Ether Wallet with a keystore" і імпортуйте в Metamask.
- Авторизуйтесь контракти в Keep Dashboard (зараз тестова мережа, пізніше основна мережа), отримаєте кілька KEEP і ETH тестової мережі і делегуйте ETH за допомогою Dashboard.
- Використовуйте VPS (Amazon, Google Cloud, Azure, Vultr, Digital Ocean, Linode, або будь-який інший), що працює на Ubuntu, встановіть Docker.
- Запустіть Keep Ноди.


?> [Keep Tools Guide] (https://keeptools.org/) дозволяє згенерувати деякі файли, необхідні для запуску, і включає деякі [Docker команди] (https://keeptools.org/docker-commands).

## Офіційні міркування Keep Network про Random Beacon ноді
Ви можете знайти офіційну документацію ** Запуск Random Beacon ** в Keep Network [тут] (https://docs.keep.network/run-random-beacon.html).
Це технічне пояснення запуску Ноди, але воно не призначене для новачків.
> Keep Network вимагає опеределнного забезпечення для кожної ноди, що працює в мережі.

> - Вкрай важливо, щоб Ноди Keep залишалися доступними для Keep Network. Ми настійно рекомендуємо стабільне і резервне підключення до Інтернету.
> - Підключайтеся на власному хостингу або VPS.
> - Основне і резервне сховище, яке витримає ротацію віртуальної машини, а також відмова диска.
> - Кожен Random Beacon, що працює в мережі, вимагає унікальної облікового запису оператора Ethereum.
> - Кожному Random Beacon, що працює в мережі, потрібно унікальний IP-адреса або унікальний порт додатки, що працює під тим же IP.


## Гайд для абсолютних новачків

- ** Nick Grego's ** [Step-by-step guide for installing both ECDSA & Beacon Keep Network nodes on VPS with 100 $ voucher] (https://medium.com/@nickgrego/step-by-step-guide- for-installing-both-ecdsa-beacon-nodes-on-vps-with-100-voucher-db930ab2a667)
> Це покрокове керівництво для новачків по запуску своїх перших нод в Keep Network з повністю безкоштовним сервером VPS і з мінімальним використанням командного рядка.

Nick's гайд (Gregory # 6997 в Discord) зробив скріншоти для кожного кроку і приклади логів, де ви можете переконатися, що все працює нормально.

- ** Ben Longstaff's ** [A beginners quick start guide to staking on the Keep Network testnet using DigitalOcean] (https://medium.com/@ben_longstaff/a-beginners-quick-start-guide-to-staking-on -the-keep-network-testnet-using-digitalocean-5a74ca60adc3)

Інше відоме керівництво для початківців, також з легкими для розуміння скриншотами, що пояснюють кожен крок.

- ** JackRemix '** [The absolute beginner's guide to Playing for Keeps] (https://medium.com/@jack.baldwin/the-absolute-beginners-guide-to-playing-for-keeps-aea9ab32f6e8) * * дійсно вражає **

## Інші гайди

- ** Alex Novy's ** [Run Random Beacon in KEEP Network Testnet] (https://medium.com/@novysf/run-a-keep-network-testnet-node-37096946af35)

Для цього керівництва ви вже повинні мати VPS.

- ** Chris Projecttent's ** [Deploy a Random Beacon Node on the Keep Testnet] (https://medium.com/@projecttent/deploy-a-random-beacon-node-on-the-keep-testnet-6c95d742fa5a) and [Deploy a Keep ECDSA Node on the Keep Testnet] (https://medium.com/@projecttent/deploy-a-keep-ecdsa-node-on-the-keep-testnet-13f374b0c11a).

Вимоги до обладнання трохи вище, ніж у інших, але, з іншого боку, вам не потрібна обліковий запис Infura.

- ** Afmsavage's ** [Keep Ecdsa Node] (https://gist.github.com/afmsavage/8fc19937a6b263f05c3e215d8860629c).

Pantsme # 2124, з Discord, розробив це керівництво як покрокове керівництво по запуску Ноди Keep-ECDSA для основної або тестової мережі, що дуже зручно для виявлення основних відмінностей між обома розгортання.

- ** Papyasha's ** [Deploy Edcsa and Random Beacon Nodes] (https://gist.github.com/papyasha/49925cf882545dada27b3f3fb7f48304).

Передбачається, що у вас вже виконана підготовча робота, тобто VPS під управлінням Linux, Infura, Wallet і інші попередні кроки.

## ECDSA нода на Amazon

- ** Afmsavage's ** [KEEP-ECDSA Node Terraform for AWS] (https://github.com/afmsavage/keep-ecdsa-tf/tree/testnet). Проходить через настройку Amazon, яка включає вбудовані електронні повідомлення про статус вашої Ноди.

## Гайди по скриптам
Скрипти допомагають автоматизувати покроковий процес налаштування Ноди ECDSA на сервері.

- ** Jeremyid's ** [Easy Keep Nodes] (https://github.com/jeremyid/easy-keep-nodes). Experience # 2376 зробив дійсно прості скрипти для обох нод.

- ** Crypto Enthu's ** [Keep Network - ECDSA Node Setup Guide] (https://medium.com/@cryptoenthu1/keep-network-ecdsa-node-setup-5164b7c2cec3) і його [репозиторій] (https: // github.com/cryptoenthu1/keep-ecdsa-repo) Naga # 0916.

- ** Finally-get-it's ** Скрипти для [Random Beacon] (https://github.com/finally-get-it/keep-rb-repo) і [Edcsa Node] (https://github.com / finally-get-it / keep-ecdsa-repo) від Ingag # 8096. Ці керівництва / репозиторії засновані на керівництві Crypto Enthu, що дозволяє змінювати ім'я проекту і порти.

- ** DaniellMesquita's ** [Keep Bot Node Installation Script] (https://github.com/DaniellMesquita/keepbot), як він каже: Абсурдно простий скрипт для настройки вашої мережі KEEP і нод tBTC.

## Kubernetes гайд для ECDSA Ноди
Запуск в кластері Kubernetes забезпечує резервний для підвищення надійності. Якщо нода виходить з ладу - на її місце запускається резервна копія.
Алекс Кроу написав це відмінне керівництво по запуску Ноди ECDSA в Kubernetes, включаючи [Helm Charts] (https://github.com/ajcrowe/keep-helm-chart) і моніторинг за допомогою Prometheus & Grafana.
[Deploy a KEEP Node to Kubernetes and Monitor with Prometheus & Grafana] (https://medium.com/@alex.j.crowe/deploy-a-keep-node-to-kubernetes-and-monitor-with-prometheus- grafana-4ee5c7d9e9a4)


## Відео

- ** Bakarapara's ** [Video walkthrough of Alex Novy's Guide] (https://youtu.be/7zgXxqnYF_0). Немає звуку, все зображення. Легко зрозуміти.

## Keep на Windows

- [Running an ECDSA Keep locally hosted, testnet node on Windows for noobs] (https://docs.google.com/document/d/1hsI8AtUiGAfcHxik-3akSRjysC0Zw0CVmHxmbNtZyHI/edit#). Деякі дані (контракти і бенкети) можуть бути застарілими. Але корисно, якщо ви хочете провести кілька тестів на комп'ютері.

`Джерело з офіційної документації Keep Team, відредагований і доповнений спільнотою. '[Джерело] (https://keep-network.gitbook.io/staking-documentation/) `

`Автори: Ramaruro, EstebanK`
`Переклад: ingag`
