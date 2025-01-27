---
id: performance_benchmark
title: Тест производительности
---

import useBaseUrl from '@docusaurus/useBaseUrl';

Вы можете убедиться, что ваш сервер соответствует [требуемым техническим характеристикам](/node_setup#00-required-technical-specifications), выполнив тест производительности. Для этого выполните следующие действия:

```bash
# Получить исходный код последней стабильной версии
$ git clone https://github.com/galacticcouncil/HydraDX-node -b stable
$ cd HydraDX-node/

# Подготовьтесь к запуску теста
$ ./scripts/init.sh
$ rustup default nightly
$ apt install python3-pip
$ pip3 install bench-wizard

# Запустите тест
$ ./scripts/check_performance.sh
```

После выполнения теста вы должны увидеть результат, подобный следующему:

```
         Pallet          |   Time comparison (µs)    |     diff*     |            |   Rerun
amm                      |    1066.00 vs 1045.80     |      20       |     OK     |
exchange                 |    1105.00 vs 1049.10     |      55       |     OK     |
transaction_multi_payment|     289.00 vs 279.96      |       9       |     OK     |
```

Если значения в поле `diff` положительны во всех трех случаях, значит, ваш компьютер подходит для запуска узла валидатора HydraDX.

Присоединяйтесь к нам в Discord, если вы хотите обсудить результаты своих тестов, наше сообщество всегда рады помочь.
