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
