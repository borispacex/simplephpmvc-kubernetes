# Ejecutando esta aplicación

- Ejecute los siguientes comandos después de iniciar minikube.

```bash
# Implementar secrets.yaml y configmap.yaml
kubectl apply -f secrets.yaml -f configmap.yaml

# Cree un mapa de configuración desde nw201402.sql dentro del clúster
kubectl create configmap mysql-init-config --from-file=nw201402.sql

# SSH en el nodo, cree el directorio de montaje del volumen hostPath y salga
minikube ssh

sudo mkdir /mnt/data

exit

# Crear volumen persistente y reclamo de volumen persistente
kubectl apply -f simplephpmvc-app-pv.yaml -f simplephpmvc-app-pvc.yaml

# Implementar las implementaciones y servicios.
kubectl apply -f simplephpmvc-app-deployment.yaml -f simplephpmvc-app-db-deployment.yaml
```
