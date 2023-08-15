# Nombre de la asignación

Participantes
- Angel Juan Martínez García
- Carlos Alberto Rodriguez Gonzalez

Actividades
- Actividad

Comandos
    kubectl get nodes
    # Clone the repository
    cd ~
    git clone https://github.com/jpetazzo/container.training

    # p. 412 - Running the application
    kubectl apply -f ~/container.training/k8s/dockercoins.yaml

    # p. 425 - Our application at work
    # Check the application logs
    kubectl logs deploy/worker
    kubectl logs deploy/hasher

    # p. 426 - Connecting to the web ui
    kubectl get svc webui
    curl <ClusterIP>

Recursos externos
- Recurso externo

Artifactos
- Anexar artifactos al directorio de respuesta


OUTPUT 

Last login: Tue Aug 15 00:44:33 2023 from 127.0.0.1
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ kubectl get nodes
NAME    STATUS   ROLES           AGE    VERSION
test1   Ready    control-plane   121m   v1.27.4
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ cd ~
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ git clone https://github.com/jpetazzo/container.training
Cloning into 'container.training'...
remote: Enumerating objects: 18915, done.
remote: Counting objects: 100% (734/734), done.
remote: Compressing objects: 100% (380/380), done.
remote: Total 18915 (delta 355), reused 587 (delta 301), pack-reused 18181
Receiving objects: 100% (18915/18915), 37.10 MiB | 30.91 MiB/s, done.
Resolving deltas: 100% (13375/13375), done.
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ kubectl apply -f ~/container.training/k8s/dockercoins.yaml
deployment.apps/hasher created
service/hasher created
deployment.apps/redis created
service/redis created
deployment.apps/rng created
service/rng created
deployment.apps/webui created
service/webui created
deployment.apps/worker created
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ kubectl logs deploy/worker
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ kubectl logs deploy/hasher
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ kubectl get svc webui
NAME    TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
webui   NodePort   10.110.154.1   <none>        80:30160/TCP   57s
[54.214.172.178] (kubernetes-admin@kubernetes:N/A) k8s@test1 ~
$ curl 10.110.154.1
curl: (7) Failed to connect to 10.110.154.1 port 80 after 0 ms: Connection refused