# viktorsheshenya_infra
viktorsheshenya Infra repository

### Данные IP
```
bastion = 104.155.63.37
someinternalhost = 10.132.0.3
```

### 1. Подключения к someinternalhost в одну команду
```
ssh -i ~/.ssh/id_rsa -J Turbo@104.155.63.37 Turbo@someinternalhost
```

### 2. Доп. задание
```
touch ~/.ssh/config
```

#### Добавляем в config
```
Host bastion 
    User Turbo
    HostName 104.155.63.37

Host someinternalhost
    User Turbo
    Hostname 10.132.0.3
    ProxyCommand ssh bastion nc %h %p
```
#### Подключение выполняется по алиасу
```
ssh someinternalhost
```