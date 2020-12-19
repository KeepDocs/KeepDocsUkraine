# Введення в tBTC & Keep Network


## DeFi
Децентралізовані фінанси (DeFi) це система відкритих і взаіосвязанних фінансових послуг і продуктів, створених і працюючих в мережі Ethereum. До липня 2020 року, майже 4 мільярди доларів задіяні у всіх додатках DeFi, що пропонують позики, токени, деривативи, обміни через децентралізовані смарт-контракти. Цей обсяг продовжує зростати.

Протоколи DeFi мають модульну структуру, що дозволяє їм взаємодіяти один з одним, створюючи все більш складну систему. Оскільки DeFi продукти - це код, який знаходиться в мережі блокчейн, такий як Ефіріум (Ethereum), вони ніколи не зможуть бути відключені або приховані від тих, кіт хоче ними скористатися. Таки чином, будь-який, хто має доступ в інтернет, може користуватися послугами кредитування, комплексними фінансовими продуктами, заощадженнями, інвестиційними та трейдингових можливостями на DeFi.

## Наміри tBTC
Незважаючи на експоненціальне зростання проектів в DeFi і Ефіріум, на біткоіни все-ще припадає дві третини загального обсягу криптовалюта в міре.a

Як Ільяс Хаціс представляє tBTC в своєму [блозі (англ.)] (Https://medium.com/@iliashatzis/could-bitcoin-on-defi-displace-banks-yes-4c0ad99f0da4):
> "Біткоіни DeFi мрія біткойнеров. Можемо мрія здійснилася і новий tBTC проект принесе Bitcoin в світ DeFi.
> Біткоіни може сильно трансформувати DeFi і це прекрасно розуміють у команді Keep. "

Команда Keep запустила tBTC, децентралізовану, надійну і застраховану систему зберігання біткоіни в токенах TBTC Ethereum ERC-20, з курсом 1: 1 до BTC. Власники біткойнов, які хочуть витратити свої BTC на Ethereum і DeFi, не повинні довіряти зберігачам (підписанти), тому що підписують сторони повинні внести заставу, що перевищує вартість BTC, яку вони тримають на зберіганні.

?> Чудова [відео (англ.)] (Https://www.youtube.com/watch?v=cfmQiArg3B8) про це від Artem # 4718 а Discord.

Підписанти вибираються випадковим чином з більш великої мережі для підписують вузлів і працюють в групах по три. Застава гарантує, що поведінка підписують сторін в системі залишається чесним, з ризиком втрати їх застави в разі шахрайства або недостатнього забезпечення. Якщо підписують сторони перемістять засобу без дозволу, залишивши на зберіганні більше TBTC, ніж BTC, система забирає їх заставу, щоб купити і знищити еквівалент TBTC з ринку, в результаті чого кількість TBTC і BTC на зберіганні врівноважити.

<P align = "center">
  <Img width = "619" alt = "Beacon" src = "https://user-images.githubusercontent.com/68087535/88100735-57075f80-cb73-11ea-996f-ec2d9590b073.png">
</ P>


## Keep Network

tBTC - це додаток в [Keep Network] (https://keep.network), якому Бен Лонгстафф дав відмінне [визначення (англ.)] (https://medium.com/@ben_longstaff/secure-multi-party-computation -smpc-explained-visually-ecde155fc7c0):

> "Keep Network має намір стати рішенням для забезпечення конфіденційності для безпечного зберігання даних поза мережею, і при цьому значно розширює функціональність смарт-контрактів і масове впровадження технології блокчейн."

Keep Network - це рішення для забезпечення конфіденційності, в якому зберігаються розподілені невеликі обсяги даних, такі як приватний ключ, і підтримується взаємодія між ланцюжками. Keeps - це смарт-контракти, які дозволяють іншим смарт-контрактами безпечно взаємодіяти з особистими даними. Вони побудовані на ECDSA алгоритмі, що підтримується багатьма провідними блокчейнамі, і полегшують підписання децентралізованих груп за допомогою багатосторонніх порогових підписів.

Keep Network в [Messari] (https://messari.io/article/announcement-messari-adds-11-new-disclosures-registry-participants-surpassing-50-members) відкритий зареєстрований учасник. Приєднавшись до цього реєстру, ці проекти взяли на себе зобов'язання підвищити рівень прозорості кріптоактівов за рахунок постійного розкриття інформації.

[Keeps Grants Explorer] (https://explorer.keep-grants.info/) від MutedTommy # 3155 (в Discord) відстежує розподілені гранти KEEP в токенах.

### t-ECDSA нода

T-ECDSA keep забезпечує безпеку транзакцій за допомогою декількох індивідуальних ключів, що зберігаються декількома підписантами. Децентралізована підпис виконується за допомогою sMPC (безпечне багатостороннє обчислення) для обчислень на загальних ключах, не розкриваючи їх. Відповідальність за підписи розділена, і потрібна певна кількість учасників для створення підпису.

Загалом, це працює так: смарт-контракт Ethereum просить Keep Network відкрити новий t-ECDSA Keep. Це сховище підтримується групою випадково обраних підписантів з кластера sMPC, більш великої мережі підписують вузлів. Ці підписують особи використовують t-ECDSA для генерації ключа і надання підпису. Підписанти можуть підписувати всі що завгодно, включаючи транзакції блокчейна. Смарт-контракт Ethereum може попросити keep підписати транзакцію на будь-якому блокчейне на основі ECDSA, біткойнов - лише один з них.

Цей механізм надійно, так як підписанти незалежні; це люди і організації запустили ноду з sMPC кластером.

<P align = "center">
  <Img width = "319" alt = "Beacon" src = "https://user-images.githubusercontent.com/68167410/88845610-05ca2200-d1aa-11ea-9d8b-400516fed25c.png">
</ P>

### Random Beacon нода

Random Beacon (випадкові маяки) інша складова цієї мережі: децентралізований інструмент випадкового вибору підписантів способом. Цей маяк - BLSThreshold Relay, їм не можна керувати або маніпулювати. Це надійне джерело випадковості, щоб вибрати одержувачів. Ніхто не знає, ким будуть підписують особи, включаючи самих підписують осіб, до того моменту, поки вони не будуть обрані випадковим маяком. Це гарантує, що підписують сторони не зможуть вступити в змову з метою крадіжки коштів або атак на мережу, і саме тому так важлива справжня випадковість, яка надається маяком.

** Random Beacon і t-ECDSA Keeps ядро ​​в мережі Keep. **



***

** Джерела і корисна інформація: **
- [Could Bitcoin on DeFi displace banks? Yes] (https://medium.com/@iliashatzis/could-bitcoin-on-defi-displace-banks-yes-4c0ad99f0da4) by Ilias Hatzis
- [Bridging Bitcoin and Ethereum] (https://blog.keep.network/bridging-bitcoin-and-ethereum-b2f9923630a7) from the Keep Network Blog
- [Secure Multiparty Computation] (https://medium.com/@ben_longstaff/secure-multi-party-computation-smpc-explained-visually-ecde155fc7c0) by Ben Longstaff
- [Building Bridges between Blockchains with tECDSA keeps] (https://blog.keep.network/building-bridges-between-blockchains-with-t-ecdsa-keeps-e58d6debb8fd) by Piotr Dyraga from the Keep Network Blog
- [Staking Documentation] (https://keep-network.gitbook.io/staking-documentation/) from the Keep Network Documentation
- [tBTC Technical Overview] (https://tbtc.network/developers/tbtc-technical-system-overview/) from the tBTC Website
- [What's in a beacon] (https://blog.keep.network/whats-in-a-beacon-12c34b0bc078) by Antonio Salazar Cardozo from the Keep Network Blog
- [Why is Trusted Randomness So Important?] (Https://blog.keep.network/why-is-trusted-randomness-so-important-c22de1c1c5ee) by Antonio Salazar Cardozo from the Keep Network Blog
- [Threshold ECDSA - Safer, more private multi-signatures] (https://blog.keep.network/threshold-ecdsa-safer-more-private-multi-signatures-51153f3e9ed2) by Antonio Salazar Cardozo from the Keep Network Blog on Keep developer Piotr Dyraga's presentation on threshold-ECDSA from San Francisco Blockchain Week 2018.
- [Defi explained] (https://decrypt.co/resources/defi-decentralized-finance-explained-guide-learn) by Decrypt.co
- [What is Defi] (https://defipulse.com/blog/what-is-defi/) by Defipulse
- [Keep promo video] (https://www.youtube.com/watch?v=h2IErqf-VrQ) by Lelka Bo in Discord Design Channel
- [TBTC: A New Sidechain Design for Bitcoin] (https://insights.deribit.com/market-research/a-new-sidechain-design-for-bitcoin/) by Su Zhu in Deribit Insights
- Images are from SpaceWalker (Discord Design Channel), [Ilias Hatzis] (https://medium.com/@iliashatzis) (from his story), Keep Team (Discord Design Channel).

---
`Джерело з офіційної документації Keep Team, відредагований і доповнений спільнотою. '[Джерело] (https://keep-network.gitbook.io/staking-documentation/) `

`Автори: Ramaruro, EstebanK`
`Переклад: ingag`
