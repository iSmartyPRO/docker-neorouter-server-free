# Краткое описание
Бесплатный VPN сервер для организации небольшой сети.


# Как пользоваться

## Установка
```
docker run -d -p 32976:32976 -v /neorouter:/usr/local/ZebraNetworkSystems/NeoRouter --name neorouter-server qlustor/nrserver-free
```

## Удаление
```
docker stop neorouter-server
docker rm neorouter-server
```

# Первоначальные настройки
Для выполнения первоначальных настроек, необходимо войти в контейнер и выполнить соответствующие настройки:
```
docker exec -ti neorouter-server sh
```

## Создание пользователя
```
nrserver -adduser admin password admin
```

## Настройка сети
```
nrserver -dhcp 10.10.10.0 255.255.255.0
```

## Посмотреть настройки
```
nrserver -showsettings
```