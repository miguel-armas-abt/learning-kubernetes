# KUBECTL

[← Regresar a notas](../../README.md) <br>

----

| k8s-object        | Objeto                    |
|-------------------|---------------------------|
| `pods`            | Pod                       |
| `service`         | Service                   |
| `deployment`      | Deployment                |
| `secret`          | Secret                    |
| `cm`              | Config Map                |
| `pv`              | Persistent Volume         |
| `pvc`             | Persistent Volume Claim   |
| `hpa`             | Horizontal Pod Autoscaler |
| `serviceaccounts` | Service Accounts          |


> ### ▶️ Mostrar objetos
> - Utilice `-A` equivalente a `--all-namespaces` para mostrar los objetos de todos los namespaces
> - Utilice `-o yaml` para formatear la respuesta
> - Utilice `-w` equivalente a `watch` para mostrar en tiempo real el estado de los objetos
> ```shell script 
> kubectl get all -n <namespace> # mostrar todos los objetos
> kubectl get <k8s-object> -n <namespace>
> ```
----

> ### ▶️ Mostrar logs del contenedor asociado a un pod
> - Utilice `-f` para seguir los logs en primer plano.
> ```shell script 
> kubectl logs -f <pod-id>
> ```
----

> ### ▶️ Port forwarding
> ```shell script 
> kubectl port-forward <pod-id> <local-port>:8080 -n <namespace>
> kubectl port-forward svc/<service-name> <local-port>:8080 -n <namespace>
> ```
---

> ### ▶️ Ingresar al sistema de archivos del contenedor asociado a un pod
> - Cambie al tipo de terminal instalada en los contenedores (`bash`, `sh`)
> ```shell script 
> kubectl exec -it <pod-id> -n <namespace> -- bash
> ```
----

> ### ▶️ Aplicar / Eliminar manifiestos
> - Utilice `-f` para indicar el directorio o nombre de los manifiestos
> ```shell script 
> kubectl apply -f <directory-name> -n <namespace>
> kubectl delete -f <directory-name> -n <namespace>
> ```
> Ejemplos: <br>
> - `kubectl apply -f ./`
> - `kubectl delete -f ./deployment.yml`
----

> ### ▶️ Modificar objetos
> - `edit` permite abrir un editor de texto para inspeccionar el manifiesto completo y efectuar cambios donde corresponda. K8s reemplaza el manifiesto entero.
> - `patch` permite actualizar solo los cambios que se especifiquen.
>
> ```shell script 
> kubectl edit <k8s-object> <k8-object-id> -n <namespace>
> kubectl patch <k8s-object> <k8s-object-id> -n <namespace> --patch '$(cat k8s-manifest.yaml)'
> ```
----

> ### ▶️ Describir / Eliminar objetos
>  
> ```shell script
> kubectl describe <k8s-object> <k8s-object-id> -n <namespace>
> kubectl delete <k8s-object> <k8s-object-id> -n <namespace>
> ```
----

> ### ▶️ Gestionar deployment
> - **Historial**: Mostrar el historial de revisiones
> - **Rollback**: Revertir el deployment a una revisión anterior
> - **Estado**: Mostrar el estado de un despliegue en curso
> - **Reinio**: Reiniciar el deployment (útil cuando se actualizan secretos)
> - **Escalado**: Escalar el deployment a N réplicas
> ```shell script 
> kubectl rollout history deployment/<deployment-id>
> kubectl rollout undo deployment/<deployment-id> --to-revision=<revision-number>
> kubectl rollout status deployment/<deployment-id>
> kubectl rollout restart deployment/<deployment-id>
> kubectl scale deployment/<deployment-id> --replicas=3
> ```
----

📋 **Persistent Volume (PV)**:
<br>Para verificar si un `PV` está siendo utilizado por algún `PVC`, puedes describirlo y buscar el campo `Claim`.
- Si `Claim` es el nombre de un PVC, entonces está siendo utilizado.
- Si `Claim` es `<none>`, entonces no está siendo utilizado.

📋 **Persistent Volume Claim (PVC)**
<br> Para verificar si un `PVC` está utilizando algún `PV`, puedes describirlo y buscar el campo `VolumeName`.
- Si `VolumeName` es el nombre de un PV, entonces está utilizándolo.
- Si `VolumeName` es `<nil>`, entonces no está utilizando ninguno.




