# BTC Watcher

`BTC Watcher` синхронизирует состояние `BTC Node` с БД `BTC` в MongoDB.

- Метод защиты от смены лучшей цепи? ждать 6 блоков до начала синхронизации?
- `BTC Watcher` загружает запись о последнем обработанном блоке
- Если последний обработанный блок меньше нового (пришедшего по ZMQ) больше чем на 2, 
то это игнорируется и он последовательно догоняет текущее состояние.

- `BTC Watcher` записывает заголовок блока в бд и загружает каждую транзакцию этого блока из кошелька
- если транзакция есть в кошельке то это наша (имеет отношение к wallet.dat) транзакция и она сохраняется в БД

- Режим работы с сохранением всех блоков и всех транзакций скорее всего избыточен 
и нужен только для эксплореров и анализа данных

https://degreesofzero.com/article/streaming-transactions-from-bitcoind-via-zeromq.html
https://www.npmjs.com/package/zeromq

√ https://bitcoindev.network/accessing-bitcoins-zeromq-interface/

```bash
git clone https://github.com/an-ivannikov-dev/btc-watcher
cd btc-watcher
yarn install
yarn start
```
