# xakaton-bimit-edge

## Подготовка проекта

Установить postgres
 - Завести пользователя: xakaton
 - Завести базу данных: xakaton
 
Установить брокер (например MQTT брокер Mosquitto)


## Запуск проекта из docker'а

Минимальный запуск
```
docker run -p 8080:8080 -e DATABASE=//IP_ADRESS:5432/xakaton  docker.pkg.github.com/maks-master/xakaton-bimit-web/docker-xakaton-web:work
```

Все параметры
```
docker run --name docker-xakaton-web -p 8080:8080 -e DATABASE=//IP_ADRESS:5432/xakaton --rm -d -v ./logs:/usr/local/tomcat/logs  docker.pkg.github.com/maks-master/xakaton-bimit-web/docker-xakaton-web:work
```


## Сборка проекта

Клонируем
```
git clone https://github.com/maks-master/xakaton-bimit-web.git
```
```
cd ./xakaton-bimit-web
```
Сборка
```
mvn clean package -Pprod
```
Результат
```
./xakaton-bimit-web/target/xakaton.war
```

Используем сборку Dockerfile