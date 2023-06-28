# tendermint_devnet

Tendermint devnet из двух нод, для разработки и тестирования технологии блокчейн.

## Перед началом

Следует убедиться, что на машинах который будет производится запуск блокчейн нод установлен Докер.

## Для деплоя 2 нод на одной машине переходим в директорию и запускаем композ проект

```
docker-compose up -d
```
## Для деплоя на разных машинах, требуется копировать репозиторий на каждую машину, предварительно раскомментировать строки с адресами нод в docker-compose.yml, а так же указав там ip адрес машин
```
      # extra_hosts:
      #   - "node0:${node0_addr}"
      #   - "node1:${node1_addr}"
```
## Затем запускать композ проект с названием соответствующей ноды на каждой машине
```
docker-compose up -d node0

#на другой машине соответственно
docker-compose up -d node1
```
## Чтобы отключить ноды выполним команду

```
docker compose down

```

## По данным адресам отображаются метрики ноды, если удаленная машина то соответственно вместо localhost прописываем айпи адрес с машиной на которой развернута нода, эти метрики можно подключить к Prometheus

- [ ] [https://localhost:26670](https://localhost:26670) - нода_0
- [ ] [https://localhost:26671](https://localhost:26671) - нода_1



