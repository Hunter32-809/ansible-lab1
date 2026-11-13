Laboratorio: Administración de Servidores Linux con Docker y Ansible
   1. Objetivo de la práctica
   Desplegar un entorno de laboratorio compuesto por dos contenedores Linux (ubuntu:24.04) mediante Docker Compose y automatizar tareas de administración, creación de directorios, generación de archivos y ejecución            condicional utilizando Ansible.

   2. Comandos para iniciar los contenedores
   Levantar los servidores en segundo plano:

Bash

   docker compose up -d
   Verificar que ambos contenedores estén activos:

Bash

   docker ps
   Instalar Python 3 en cada contenedor (requerido por Ansible):

Bash

   docker exec server1 bash -c "apt update && apt install -y python3"
   docker exec server2 bash -c "apt update && apt install -y python3"
   3. Comando para ejecutar el playbook
   Comprobar conectividad con los nodos del inventario:

Bash

   ansible docker -i inventory.ini -m ping
   Ejecutar el playbook de configuración:

Bash

   ansible-playbook -i inventory.ini playbook.yml


<img width="992" height="770" alt="image" src="https://github.com/user-attachments/assets/76aa5389-f233-4d3c-8e92-42c62ea78e96" />



<img width="1066" height="751" alt="image" src="https://github.com/user-attachments/assets/864f57b8-5841-403d-993e-681b8d06c8b5" />
