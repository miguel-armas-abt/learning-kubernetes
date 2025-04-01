# CONFIGURACIÓN

[← Regresar a notas](../../README.md) <br>

----

> ### ⚙️ Instalar Kubectl y Minikube
> Referencias:
>   - [Instalar Kubectl y Minikube](https://youtu.be/hPlioIpgTuQ?si=VHKb_K0cKTd_-4aK)

> ### ▶️ Mostrar información del clúster
> ```shell script 
> kubectl cluster-info            # mostrar información del clúster
> kubectl config view             # mostrar configuración del clúster
> kubectl get nodes               # mostrar nodos
> kubectl kubectl api-versions    # mostrar versión del API Server
> ```
----

> ### ▶️ Gestión de contextos
> ```shell script 
> kubectl config current-context            # mostrar contexto actual
> kubectl config get-contexts               # mostrar contextos
> kubectl config use-context <context-name> # cambiar de contexto
> ```
> Ejemplos:<br>
> - `kubectl config use-context minikube`
> - `kubectl config use-context askeu2008pocdev02`

---

> ### ▶️ **Gestión de namespaces**
> ```shell script
> kubectl create namespace <namespace>
> kubectl delete namespace <namespace>
> kubectl get events -n <namespace>     # mostrar eventos en un namespace
> ```