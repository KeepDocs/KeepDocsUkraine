# Моніторинг та оповіщення

У цьому розділі розглядаються такі теми, пов'язані з методами автоматичного моніторингу нод і віддаленого оповіщення.

** Зміст цього розділу **
- [Гайд по налаштуванню моніторингу Keep нод (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Monitoring-and-Remote-Alerting#guides-for-setting-up-node- monitoring-of-keep-nodes)
- [Discord і Telegram боти (англ.)] (Https://github.com/Estebank97/Keep-Node-Operation/wiki/Monitoring-and-Remote-Alerting#discord-and-telegram-bots-to-get- keep-network-stats)

## Гайд по налаштуванню моніторингу Keep нод
### Random Beacon моніторинг, використовуючи Grafana, Prometheus, Prometheus Node Exporter, Google cAdvisor і Loki
- MutedTommy's [Keep Random Beacon | Node Monitoring | Part 1] (https://medium.com/@hr12rtk/keep-random-beacon-node-monitoring-grafana-prometheus-and-loki-4a4b669b31ea) and [Part 2] (https://medium.com/@ hr12rtk / keep-random-beacon-node-monitoring-part-2-5cd037464a6e).
У цій статті коротко описані кроки для настройки моніторингу на Keep Random Beacon ноді, використовуючи Grafana, Prometheus, Prometheus Node Exporter, Google cAdvisor і Loki.

<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/89043879-c537e900-d30e-11ea-84ad-dfbd47592d2f.png">
</ P>


### Random Beacon і ECDSA моніторинг нод, використовуючи Elasticsearch, Logstash, і Kibana
- Гайд по [Настройці Elastic Stack Dashboard (англ.)] (Https://www.notion.so/Setting-up-Elastic-Stack-Dashboard-14f9edc94418468bb95af40417a0332a) для Keep Random Beacon і ECDSA нод, використовуючи Elasticsearch, Logstash, і Kibana

> Elastic Stack - також званий ELK Stack - це добірка програмного забезпечення з відкритим вихідним кодом, розробленого Elastic, який дозволяє вам шукати, аналізувати і візуалізувати логи, створені з будь-якого джерела в будь-якому форматі. Централізоване ведення логів може бути дуже корисно при спробі визначити проблеми з вашими серверами або додатками, оскільки воно дозволяє вам шукати по всім вашим логам в одному місці. Це також корисно, оскільки дозволяє виявляти проблеми, що охоплюють кілька серверів, шляхом зіставлення їх логів по певному періоду часу.
>
> [Elastic Stack] (https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-elastic-stack-on-ubuntu-18-04#step-4- % E2% 80% 94-installing-and-configuring-filebeat) має чотири основні компоненти:
>
> Elasticsearch: пошукова система RESTful, в якій зберігаються всі зібрані дані.
>
> Logstash: компонент обробки даних Elastic Stack, який відправляє вхідні дані в Elasticsearch.
>
> Kibana: веб-інтерфейс для пошуку і візуалізації логів.
>
> Beats: одноцільові постачальники даних, які можуть відправляти дані з сотень або тисяч машин в Logstash або Elasticsearch.
>
<P align = "center">
  <Img width = "800" src = "https://user-images.githubusercontent.com/68167410/89001980-816ac280-d2c1-11ea-98f2-94e0481188fc.png">
</ P>


## Discord і Telegram для отримання статистики від Keep Network
Деякі боти розроблені для використання в [Keep Discord Channel] (https://discord.com/channels/590951101600235531/709789601459339326). Найближчими місяцями повинні з'явитися оновлення.

[KEEP BOT] (https://discord.com/channels/590951101600235531/709789601459339326/735597811613302855) by StateLayer

Список команд для бота
Keep Network Bot (StateLayer)
-! Keep all: Show all network stats
-! Keep price: $ KEEP price
-! Keep volume: KEEP 24h volume
-! Keep stakers: number of stakers on the network
-! Keep holders: Amount of holders of KEEP
-! Keep staked: Amount of KEEP staked in the random beacon contract
-! Keep stakedropreserve: Amount of KEEP in the stakedrop reserve
-! Keep liquidityreserve: Amount of KEEP in the liquidity reserve
-! Keep beacontransactions: Total number of random beacon transactions
-! Keep exchanges: show keep balances in exchanges
-! Keep wen ICO? : (Hint, never)

Моніторинг нод (StateLayer)
 (ЛЗ боту)
-! Watcher summary youraddress: різна статистика про вашу підписує групі
-! Watcher ethbonded youraddress: отримати баланс, пов'язаний з вашою групою
-! Watcher collateralratio youraddress: коефіцієнт застави вашої групи
-! Watcher help: показати доступні команди
Замість "youraddress", вставте ефіріум адресу вашої підписує групи.

tBTC статистика (pantsme)
Доступні команди:! Supply,! Txs,! Holders,! Tdt,! Volume,! Help

---
`Джерело з офіційної документації Keep Team, відредагований і доповнений спільнотою. '[Джерело] (https://keep-network.gitbook.io/staking-documentation/) `

`Автори: Ramaruro, EstebanK`
`Переклад: ingag`
