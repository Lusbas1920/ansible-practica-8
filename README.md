
# Práctica 8: Automatización con Ansible

## Descripción
Laboratorio de automatización con Ansible que administra cinco servidores Ubuntu 22.04 ejecutados mediante Docker Compose.

## Tecnologías utilizadas
- Ubuntu 22.04
- Docker
- Docker Compose
- OpenSSH
- Ansible

## Estructura del proyecto
```text
ansible-practica-8/
├── ubuntu/
│   └── Dockerfile
├── docker-compose.yml
├── inventory.ini
├── ansible.cfg
├── playbook.yml
└── README.md
```

## Configuración y ejecución

### 1. Iniciar los cinco servidores
```bash
docker compose up -d --build
```

### 2. Instalar Ansible y sshpass en el controlador
```bash
sudo apt update
sudo apt install ansible sshpass -y
```

### 3. Comprobar la conexión
```bash
ansible servidores -m ping
```

### 4. Ejecutar la automatización
```bash
ansible-playbook playbook.yml
```

## Tareas automatizadas
El playbook realiza las siguientes tareas en los cinco servidores:

1. Actualiza la caché de paquetes APT.
2. Crea el usuario `itla`.
3. Crea el directorio `/home/itla/app`.
4. Crea el archivo `hola.txt`.
5. Instala los paquetes `cowsay` y `htop`.

## Puertos utilizados

| Servidor | Puerto |
|---|---:|
| ubuntu1 | 2221 |
| ubuntu2 | 2232 |
| ubuntu3 | 2223 |
| ubuntu4 | 2224 |
| ubuntu5 | 2225 |

## Resultado
La ejecución del playbook fue exitosa en los cinco servidores, sin errores ni hosts inaccesibles.
