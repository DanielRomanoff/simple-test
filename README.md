<h1>Run via docker-compose:</h1>

``` shell
docker-compose up -d
```
``localhost:8080`` - application \
``localhost:9000/actuator/prometheus`` - application metrics \
``localhost:9090`` - prometheus \
``localhost:3000`` - Grafana

``admin/admin`` - Grafana login/password

<h1>Run via minicube:</h1>

```shell
minikube start
eval $(minikube docker-env)
```
```shell
docker-compose pull
docker-compose build
```
```shell
cd helm
```
```shell
helm install grafana grafana
helm install prometheus prometheus
helm install application application
```
```shell
kubectl get pods
```

Found pod with name ``grafana-***-***``

``` shell
kubectl get pods
```

``` shell
kubectl port-forward grafana-***-*** 3000
```
Login - ``admin``

Get administrator password
``` shell
kubectl get secret --namespace default grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```

``localhost:3000`` - Grafana

Find spring statistics in dashboards.




<h1>Запуск через docker-compose:</h1>

```shell
docker-compose up -d
```
``localhost:8080`` - приложение \
``localhost:9000/actuator/prometheus`` - метрики приложения \
``localhost:9090`` - prometheus \
``localhost:3000`` - Grafana 

``admin/admin`` - Grafana login/pass

<h1>Запуск через minikube:</h1>

```shell
minikube start
eval $(minikube docker-env)
```
```shell
docker-compose pull
docker-compose build
```
```shell
cd helm
```
```shell
helm install grafana grafana
helm install prometheus prometheus
helm install application application
```
```shell
kubectl get pods
```

Необходимо найти pod с именем ``grafana-***-***``

```shell
kubectl get pods
```

```shell
kubectl port-forward grafana-***-*** 3000
```
Логин - ``admin``

Получить пароль admin
```shell
kubectl get secret --namespace default grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```

``localhost:3000`` - Grafana 

Найти в dashboards spring statistic.
