
# training-ansible
Autor: Pablo Fernando Pineda P. - A00395831

## Descripción
Este proyecto utiliza Ansible para automatizar la instalación de Docker y la gestión de contenedores en servidores remotos, como máquinas virtuales en Azure. Está organizado en roles y playbooks para facilitar la administración y el despliegue.

## Requisitos
- Tener Ansible instalado en tu máquina local.
- Acceso a una máquina virtual (por ejemplo, en Azure) con SSH habilitado.
- Docker no debe estar previamente instalado en la VM.

## Estructura del proyecto
- `inventory/hosts.ini`: Archivo donde se definen los hosts (IP, usuario y contraseña de la VM).
- `playbooks/install_docker.yml`: Playbook para instalar Docker.
- `playbooks/run_container.yml`: Playbook para ejecutar y gestionar contenedores Docker.
- `roles/docker_install`: Rol con tareas para instalar Docker.
- `roles/docker_container`: Rol con tareas para gestionar contenedores.

## Pasos para la ejecución

### 1. Configurar el inventario
Edita el archivo `inventory/hosts.ini` y coloca la IP, usuario y contraseña de la máquina virtual donde se instalará Docker.

### 2. Instalar Docker
Ejecuta el siguiente comando para instalar Docker en los hosts definidos:

```bash
ansible-playbook -i inventory/hosts.ini playbooks/install_docker.yml
```
Este comando ejecuta el playbook que instala Docker en los servidores especificados en el inventario.

### 3. Ejecutar contenedores Docker
Ejecuta el siguiente comando para iniciar y gestionar contenedores Docker:

```bash
ansible-playbook -i inventory/hosts.ini playbooks/run_container.yml
```
Este comando ejecuta el playbook que inicia y gestiona contenedores Docker en los servidores definidos en el inventario.

### 4. Abrir puertos en la VM
Si la máquina virtual no tiene abiertos los puertos necesarios para acceder al contenedor, ábrelos desde el portal de Azure o usando la CLI correspondiente.

### 5. Comprobar funcionamiento
Verifica que Docker esté instalado y que el contenedor esté corriendo correctamente.

#### 5.1
```bash
docker ps
```

#### 5.2 Acceder al servicio expuesto por el contenedor




## Conclusiones
- Ansible facilita la gestión de infraestructura mediante la automatización de tareas repetitivas y la estandarización de procesos.
- El uso de roles y playbooks permite mantener el código organizado y reutilizable.
- La automatización reduce errores humanos y acelera el despliegue de servicios como Docker.
- Este proyecto ejemplifica el uso de Ansible para la automatización de configuración y orquestación de servicios en entornos cloud como Azure.


