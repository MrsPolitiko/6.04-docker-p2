# Домашнее задание к занятию "Docker часть 2" - **Политико Ксения**


### Задание 1

`Сompose это кросплатформенный инструмент для создания, запуска и администрирования многоконтейнерных приложений, создания и администрирования общих ресурсов. Вся конфигурация описывается в YAML файлах.`

---
### Задание 2

![Файл с первичными настройками](https://github.com/MrsPolitiko/6.04-docker-p2/blob/main/docker-compose-template.yml)

---
### Задание 3
![Файл с настройками Prometeus](https://github.com/MrsPolitiko/6.04-docker-p2/blob/main/docker-prometheus.yml)

---
### Задание 4
![Файл с настройками Prometeus + Pushgateway](https://github.com/MrsPolitiko/6.04-docker-p2/blob/main/docker-prometheus-gateway.yml)

---
### Задание 5
![Файл с настройками Grafana](https://github.com/MrsPolitiko/6.04-docker-p2/blob/main/docker-grafana.yml)

---
### Задание 6
Команда запуска в режиме *detached*
```
docker compose -f docker-prometheus-gateway-grafana.yml up -d
```
---
### Задание 7
Yml файл называется немного иначе, мне было так удобнее :) 
[docker-prometheus-gateway-grafana.yml целиком](https://github.com/MrsPolitiko/6.04-docker-p2/blob/main/docker-prometheus-gateway-grafana.yml)

На всякий случай вот мой запуск *писалки* в Prometeus
```
for i in {1..100}; do echo "politikoks" $(( 1 + $RANDOM % 100  )) |curl --data-binary @- http://localhost:9091/metrics/job/netology && sleep 1s;  done
```
[скриншот команды docker ps после запуска docker-prometheus-gateway-grafana.yml](https://github.com/MrsPolitiko/6.04-docker-p2/docker-prometheus-gateway-grafana.yml)

[скриншот графика, постоенного на основе вашей метрики](https://github.com/MrsPolitiko/6.04-docker-p2/blob/main/img/task_7.png)


---
### Задание 8
```
for d in $( docker ps -q ); do docker stop $d && docker rm $d; done
```

---
### Задание 9
