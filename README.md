# Домашнее задание к занятию "Docker часть 2" - **Политико Ксения**


### Задание 1

`Сompose это кросплатформенный инструмент для создания, запуска и администрирования многоконтейнерных приложений, создания и администрирования общих ресурсов. Вся конфигурация описывается в YAML файлах.`

---
### Задание 2

![Скриншот задания](https://drive.google.com/file/d/18iR1qGetOvMwOsvrZr_p1DT4uASkixJC/view?usp=sharing)

---
### Задание 3

---
### Задание 4

---
### Задание 5

---
### Задание 6

docker compose -f docker-prometheus-gateway-grafana.yml up -d

---
### Задание 7

Yml файл называется немного иначе, мне было так удобнее :)
[docker-prometheus-gateway-grafana.yml целиком](https://github.com/MrsPolitiko/6.04-docker-p2/docker-prometheus-gateway-grafana.yml)

На всякий случай вот мой запуск *писалки* в Prometeus
```
for i in {1..100}; do echo "politikoks" $(( 1 + $RANDOM % 100  )) |curl --data-binary @- http://localhost:9091/metrics/job/netology && sleep 1s;  done
```
[скриншот команды docker ps после запуска docker-prometheus-gateway-grafana.yml](https://github.com/MrsPolitiko/6.04-docker-p2/docker-prometheus-gateway-grafana.yml)

[скриншот графика, постоенного на основе вашей метрики](https://github.com/MrsPolitiko/6.04-docker-p2/docker-prometheus-gateway-grafana.yml)


---
### Задание 8
```
for d in $( docker ps -q ); do docker stop $d && docker rm $d; done
```
