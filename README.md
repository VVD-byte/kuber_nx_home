# Работу выполнили студенты Воронин и Цепилова
# Развертывание веб-приложения в Kubernetes с использованием Minikube

## Подготовка окружения
Для начала мы установили Minikube и Docker, чтобы иметь возможность создать локальный кластер Kubernetes и собрать Docker image веб-приложения.
## Запуск Minikube
Затем мы запустили Minikube, указав, что хотим использовать его в качестве драйвера для создания локального кластера Kubernetes.
## Сборка Docker Image
Далее, мы собрали и проверили работу Docker image. Также залили на docker hub
https://hub.docker.com/layers/vovavoronin/kuber_nx_home/1.0.0/images/sha256-274b76f81eb115a29550a0d051f7be60c829d64297313c269efec794147f852b?context=repo
```
docker build -t vovavoronin/kuber_nx_home:1.0.0 .
docker run -p 8000:8000 vovavoronin/kuber_nx_home:1.0.0
docker push vovavoronin/kuber_nx_home:1.0.0
```
## Пишем деплоймент (web-deployment.yaml в репе) и вносим изменения и проверяем работу (PNG со скрином в репе)
```
kubectl apply -f web-deployment.yaml
kubectl describe deployment web
```
