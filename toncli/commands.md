## Список команд 

Оригинал доступен в [официальном репозитории](https://github.com/disintar/toncli/blob/master/docs/advanced/commands.md) проекта.

|Команда | описание|
|-|-|
|`toncli` или `toncli -h`| Выводит основную информацию об использовании интерфейса|
|`toncli start [-h] [--name NAME] {wallet, external_data}`|Создает шаблон пустого проекта типа `wallet` или `external_data` (на 04.09.22 доступен только тип `wallet`) |
|`toncli deploy [contracts] [-h] [--net {testnet,mainnet,ownnet}] [--workchain WORKCHAIN] [--ton TON] [--update]`| [Деплой][deploy] [СК][sk] проекта в блокчейн. Создает [StateInit][stateinit] и внешнее сообщение, а также [boc][boc], который будет отправлен в блокчейн. Параметр `contracts` - имена контрактов для деплоя из файла _project.yaml_, `--net` - выбор сети (тестовая, основная, своя), `--workchain` - выбор воркчейна, `--ton` показывает, какое количество монет необходимо [отправить][send], `update` - обновление локального кэша состояния сети |
|`toncli build` или `toncli func build`|Сборка (build) файлов проекта, находящихся в папке _func/_ |
|`toncli get [--contract NAME] [--address ADDRESS] [GET_METHOD] [--fift FIFT]`| Запуск метода _get()_ по имени контракта (`--contract`) или по его адресу (`--address`). Если параметр `--fift` указан, будет запущен fift-скрипт, полученные данные которого будут переданы в стек |
|`toncli run_transaction [-h] [--net {testnet,mainnet,ownnet}] logical_time transaction_hash smc_address`| Отладочное сообщение по логическому времени, хешу транзакции и адресу аккаунта. Получение данных/кода/баланса аккаунта и локальный запуск транзакции |
|`toncli tointeger`| Превращение строки в тип integer для передачи ее в код FunC|
|`toncli addrs`| Получение адресов СК проекта |

|||
|-|-|
|`toncli fift [-h] [--net {testnet,mainnet,ownnet}] [--workchain WORKCHAIN] [--update] [--fift-args FIFT_ARGS] [--lite-client-args LITE_CLIENT_ARGS]`||
|`toncli fift run [--build] [files] [command lite arguments to files]`| Запуск файла fift. Если `--build` указан - перед этим будет проведена сборка |
|`toncli fift interactive`| Запуск интерактивной оболочки fift как метод по умолчанию |
|`toncli fift sendboc [files] [command lite arguments to files]`| Запуск fift-файла и отправка _boc_ в блокчейн (необходимо указать saveboc, в стеке должен быть boc) |
|`toncli f`| Можно использовать вместо `fift`|

|||
|-|-|
|`toncli lite-client [-h] [--net {testnet,mainnet,ownnet}] [--update] [--lite-client-args LITE_CLIENT_ARGS]`||
|`toncli lite-client interactive`| Запуск интерактивной оболочки lite-клиента как метод по умолчанию |
|`toncli lite-client [ANY]`| Запуск методов, аргументы будут переданы в оболочку lite-клиента (toncli lc help) |
|`toncli lc`| `lc` может использоваться вместо `lite-client` |

|||
|-|-|
|`toncli func [-h] [--func-args FUNC_ARGS] [--fift-args FIFT_ARGS] [--run]`||
|`toncli func build [file]`| Сборка файлов проекта в папке _func/_ в папку _build/_ или в файл в _cwd_ |
|`toncli func [ANY]`| `ANY` будет передано команде `func`   |
|`toncli fc`| Может использоваться вместо `func`|

|||
|-|-|
|`toncli run_tests`| Запуск тестов. [Пример](https://github.com/disintar/func-tests-playground), [разбор](https://github.com/romanovichim/TonFunClessons_ru/blob/main/2lesson/secondlesson.md)|
|`toncli send [-h] [--amount AMOUNT] [--contracts CONTRACTS] [--net {testnet,mainnet,ownnet}] [--update] [--address ADDRESS] [--mode MODE] [--body BODY] [--no-bounce NO_BOUNCE] [--force-bounce FORCE_BOUNCE]`| Отправка сообщения от кошелька, с которого производится деплой, к СК по адресу или имени СК. Можно передать код fift в тело этого сообщения (требуется `builder` в стеке) |
|`toncli build-cli-lib`| Техническая команда для создания _cli.fif_ |
|`toncli addrs`| Получение адреса СК|





>Каждую команду можно вызвать с аргументом `-h`, чтобы получить подробное описание в терминале (напр. `toncli deploy -h`).


[deploy]: /blog "загрузка смарт-контракта в блокчейн"
[sk]: /blog "смарт-контракт"
[stateinit]: /blog "Структура, которая содержит код и данные нового СК"
[boc]: /blog "bag-of-cells"
[send]: /blog "куда?"