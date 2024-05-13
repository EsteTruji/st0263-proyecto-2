# Info de la materia: ST0263 - Tópicos Especiales en Telemática

### Estudiantes:
  - Esteban Trujillo Carmona, etrujilloc@eafit.edu.co
  - Viviana Hoyos Sierra, vhoyoss@eafit.edu.co
  - Damian Duque López, daduquel@eafit.edu.co
  - Valentina Morales Villada, vmoralesv@eafit.edu.co

### Profesor: Edwin Montoya, emontoya@eafit.edu.co

# Proyecto 2 

# Video sustentación

[![Video](https://img.youtube.com/vi/6Vu73vi8l-g/0.jpg)](https://www.youtube.com/watch?v=6Vu73vi8l-g)

## 1. Breve descripción de la actividad

Se desplegó un CMS Wordpress en un clúster de alta disponibilidad en Kubernetes desplegado como IaaS (Infrastructure as a Service) montado en diferentes máquinas virtuales, con la distribución microk8s. Se consideraron además los volúmenes compartidos y la capa de acceso al clúster, Ingress.

Para el Load Balancer se instaló nginx y se configuró con un objeto Ingress que ayuda a administrar el acceso externo proporcionando reglas de enrutamiento http/s a los servicios dentro del clúster. Además está la instancia de Wordpress y la de la base de datos, en este caso MySQL y finalmente se implementó un servicio de almacenamiento distribuido NFS (Network File System).

En este proyecto hicimos uso de tecnologías como Kubernetes, proveedores de dominio como GoDaddy y servicios de Google Cloud Platform.
### 1.1. Que aspectos cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)

**NO FUNCIONALES**

-	**DISPONIBILIDAD:**
    -  Despliegue de aplicación wordpress utilizando Kubernetes.
    -  Implementación de balanceador de cargas que reciba el tráfico web http/s de Internet con múltiples instancias de procesamiento.
   

**FUNCIONALES**
- Clúster instalado en nube con mikrok8s.
- Almacenamiento en la capa de datos haciendo uso de una base de datos MySQL.
- Almacenamiento de archivos distribuido implementado haciendo uso del NFS dentro del mismo clúster.
- Conexion de servicios de wordpress con el servicio NFS.
- Certificado SSL para habilitar la conexión cifrada. (https)



### 1.2. Que aspectos NO cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)

Se cumplió con todos los requerimientos propuestos por el profesor.

## 2. Información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas.

Se implementó para este proyecto la siguiente arquitectura:

![final](https://github.com/EsteTruji/st0263-proyecto-2/assets/81714113/cd8fd171-5521-4053-a4de-90334a762d4c)


## 3. Descripción del ambiente de ejecución lenguaje de programación, librerias, paquetes, etc, con sus numeros de versiones.


**IPs utilizadas en el reto 4:**

**IPs Privadas:**

- **Servicio Kubernetes:** 10.103.192.1
- **Servicio Load balancer:** 10.103.193.248

**IPs Públicas:**
- **Servicio Load balancer:** 34.171.91.170
- **DataBase:** 35.192.174.33


Cabe resaltar que para el desarrollo y cumplimiento de este reto no fue necesario instalar ningun otro paquete o libreria adicional ya que todos los recursos utilizados son nativos de GCP.


## 4. Guía paso a paso de instalación y configuración

La guía paso a paso de este proyecto se encuentra en el archivo ```step-by-step-guide.md``` subido en este repositorio. De igual forma, se puede acceder a este desde el enlace a continuación:

[Step-by-Step-guide](https://github.com/EsteTruji/st0263-Proyecto-2/blob/main/step-by-step-guide.md)

## Referencias

[Install MicroK8s](https://microk8s.io/#install-microk8s)

[Use NFS for Persistent Volumes on MicroK8s](https://microk8s.io/docs/how-to-nfs)

[Example: Deploying WordPress and MySQL with Persistent Volumes](https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/)

[Deploying MySQL on Kubernetes](https://medium.com/@midejoseph24/deploying-mysql-on-kubernetes-16758a42a746)

[Addon: cert-manager](https://microk8s.io/docs/addon-cert-manager)






